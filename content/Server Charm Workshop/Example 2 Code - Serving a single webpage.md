This example serves a single webpage (directly from code) when a user connects to out access point

```cpp
#include <WiFi.h> // allows us to use the wifi chip on the board
#include <DNSServer.h> // NEW: allows us to make the captive portal
#include <WebServer.h> // NEW: allows us to serve webpages

#define RGB_BRIGHTNESS 1  // Change white brightness (max 255)

const char *ssid = "Server Charm Workshop!";

const byte DNS_PORT = 53;
IPAddress apIP(172, 217, 28, 1);
WebServer server(80);
DNSServer dnsServer;

// Edit this to change the website content!
const char INDEX_HTML[] PROGMEM = R"HTML(
<!doctype html>

<body>
    <h1>Welcome to my simple webpage!</h1>
    <hr>
    <p>Fabrication society is a community dedicated to bringing students of all backgrounds and disciplines to learn and connect over a shared passion over 3D printing and other kinds of fabrication!</p>
</body>

</html>
)HTML";


void setup() {

  Serial.begin(115200);
  Serial.println();
  Serial.println("Configuring access point...");
  neopixelWrite(RGB_BUILTIN, RGB_BRIGHTNESS, 0, 0);  // Make the light red to start with

  WiFi.mode(WIFI_AP);
  WiFi.setTxPower(WIFI_POWER_21dBm); // max power
  WiFi.softAPConfig(apIP, apIP, IPAddress(255, 255, 255, 0));
  if (!WiFi.softAP(ssid, NULL, 1, 0, 8)) {
    log_e("Soft AP creation failed.");
    neopixelWrite(RGB_BUILTIN, 255, 0, 0);
    while (1)
      ;
  }
  dnsServer.start(DNS_PORT, "*", apIP);


  server.onNotFound([]() {
    server.send(200, "text/html", INDEX_HTML);
    Serial.println(server.uri());

  });
  IPAddress myIP = WiFi.softAPIP();

  Serial.print("AP IP address: ");
  Serial.println(myIP);
  server.begin();

  Serial.println("Server started");
  neopixelWrite(RGB_BUILTIN, 0, 0, RGB_BRIGHTNESS);  // Make the light blue when the server is running
}

// the loop function runs over and over again forever
void loop() {
  
  if (WiFi.softAPgetStationNum() == 0) {    
    neopixelWrite(RGB_BUILTIN, 0, 0, RGB_BRIGHTNESS);  // Make the light blue when no-one is connected
    
  } else {
    neopixelWrite(RGB_BUILTIN, 0, RGB_BRIGHTNESS, 0);  // Make the light green when someone connects
    delay(100);
    dnsServer.processNextRequest();
    server.handleClient();
  }

}

```
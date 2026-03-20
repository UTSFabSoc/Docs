This example uses the SPIFFS storage partition to store website content in a proper filesystem. make sure you upload your data folder to the ESP32 before trying to run this!
```cpp
#include <WiFi.h>
#include <DNSServer.h>
#include <WebServer.h>
#include <FS.h>  // NEW: Allows us to read and write to the SPIFFS storage partition
#include <LittleFS.h> // NEW: Allows us to read and write to the SPIFFS storage partition

#define RGB_BRIGHTNESS 1  // Change white brightness (max 255)

const char *ssid = "Server Charm Workshop!";

const byte DNS_PORT = 53;
IPAddress apIP(172, 217, 28, 1);
WebServer server(80);
DNSServer dnsServer;

void setup() {

  Serial.begin(115200);
  Serial.println();
  Serial.println("Configuring access point...");
  neopixelWrite(RGB_BUILTIN, RGB_BRIGHTNESS, 0, 0);  // Red until ap is created

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

  //File system begin
  LittleFS.begin();


  server.onNotFound([]() {
    Serial.println(server.uri());
    if (!handleFileRead(server.uri())) {
      const char *metaRefreshStr = "<head><meta http-equiv=\"refresh\" content=\"0; url=http://172.217.28.1/index.html\" /></head><body><p>redirecting...</p></body>";
      server.send(200, "text/html", metaRefreshStr);
    }
  });
  IPAddress myIP = WiFi.softAPIP();

  Serial.print("AP IP address: ");
  Serial.println(myIP);
  server.begin();

  Serial.println("Server started");
  neopixelWrite(RGB_BUILTIN, 0, 0, RGB_BRIGHTNESS);  // Blue

}

// the loop function runs over and over again forever
void loop() {
  
  if (WiFi.softAPgetStationNum() == 0) {
    neopixelWrite(RGB_BUILTIN, 0, 0, RGB_BRIGHTNESS);  // Blue
  } else {
    // something connected
    
    neopixelWrite(RGB_BUILTIN, 0, RGB_BRIGHTNESS, 0);  // Green
    delay(100);
    dnsServer.processNextRequest();
    server.handleClient();
  }

}

String getContentType(String filename) {
  if (server.hasArg("download")) return "application/octet-stream";
  else if (filename.endsWith(".htm")) return "text/html";
  else if (filename.endsWith(".html")) return "text/html";
  else if (filename.endsWith(".css")) return "text/css";
  else if (filename.endsWith(".js")) return "application/javascript";
  else if (filename.endsWith(".png")) return "image/png";
  else if (filename.endsWith(".gif")) return "image/gif";
  else if (filename.endsWith(".jpg")) return "image/jpeg";
  else if (filename.endsWith(".ico")) return "image/x-icon";
  else if (filename.endsWith(".xml")) return "text/xml";
  else if (filename.endsWith(".mp4")) return "video/mp4";
  else if (filename.endsWith(".pdf")) return "application/x-pdf";
  else if (filename.endsWith(".zip")) return "application/x-zip";
  else if (filename.endsWith(".gz")) return "application/x-gzip";
  else if (filename.endsWith(".webp")) return "image/webp";
  return "text/plain";
}

//Given a file path, look for it in the SPIFFS file storage. Returns true if found, returns false if not found.
bool handleFileRead(String path) {
  if (path.endsWith("/")) path += "index.html";
  Serial.println("Trying to get: " + path);
  String contentType = getContentType(path);
  String pathWithGz = path + ".gz";
  if (LittleFS.exists(pathWithGz) || LittleFS.exists(path)) {
    if (LittleFS.exists(pathWithGz))
      path += ".gz";
    File file = LittleFS.open(path, "r");
    Serial.println("Found file, opening...");
    size_t sent = server.streamFile(file, contentType);
    file.close();
    return true;
  }
  Serial.println("Couldn't find file!");
  return false;
}

```
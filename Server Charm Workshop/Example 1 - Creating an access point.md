This example creates an access point with the provided name which users can connect to (although nothing happens when they do)
```c
#include <WiFi.h>
#include <esp_wifi.h>

#define RGB_BRIGHTNESS 1  // Change white brightness (max 255)

const char *ssid = "Server Charm Workshop!";

IPAddress apIP(172, 217, 28, 1);

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



  IPAddress myIP = WiFi.softAPIP();

  Serial.print("AP IP address: ");
  Serial.println(myIP);

  Serial.println("Server started");
  neopixelWrite(RGB_BUILTIN, 0, 0, RGB_BRIGHTNESS);  // Blue

  ;
}

void loop() {
  
  
}

```


## Setting Up ThingSpeak Server

[ThingSpeak](https://thingspeak.com) is an **IoT analytics platform** that allows you to **aggregate, visualize, and analyze live data streams** in the cloud.  
You can send data to ThingSpeak from your IoT devices, create real-time visualizations, and even set up automatic alerts and MATLAB-based analytics.

---

### 🔧 Steps to Set Up ThingSpeak Dashboard

1. **Create a ThingSpeak Account**
   - Go to [https://thingspeak.com](https://thingspeak.com)
   - Sign up or log in with your MathWorks account.

2. **Create a New Channel**
   - Click on **Channels → New Channel**
   - Enter the following parameters:
     - **Name:** Water Quality Monitoring System  
     - **Field 1:** pH Value  
     - **Field 2:** Turbidity (NTU)  
     - **Field 3:** TDS (ppm)  
     - **Field 4:** Temperature (°C)
   - You can also enable **Show Location** if your device includes GPS.
   - After entering details, click **Save Channel**.

3. **Copy the API Key**
   - Go to the **API Keys** tab in your created channel.
   - Copy the **Write API Key** — this will be used in your **Gateway (ESP32/STM32)** code to send data.

4. **Visualize the Data**
   - Once your system starts sending data, open the **Private View / Public View** tabs to see real-time graphs.
   - You can customize chart types, colors, and time windows.

---

### 🧠 Example Code Snippet (ESP32 → ThingSpeak)

```cpp
#include <WiFi.h>
#include <HTTPClient.h>

const char* ssid = "Your_WiFi_Name";
const char* password = "Your_WiFi_Password";
String apiKey = "YOUR_WRITE_API_KEY";
const char* server = "http://api.thingspeak.com/update";

void setup() {
  Serial.begin(115200);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("\\nWiFi Connected");
}

void loop() {
  if (WiFi.status() == WL_CONNECTED) {
    HTTPClient http;
    String url = String(server) + "?api_key=" + apiKey +
                 "&field1=" + String(pH) +
                 "&field2=" + String(turbidity) +
                 "&field3=" + String(tds) +
                 "&field4=" + String(temp);
    http.begin(url);
    int httpCode = http.GET();
    http.end();
  }
  delay(15000); // ThingSpeak allows 1 update every 15 seconds
}

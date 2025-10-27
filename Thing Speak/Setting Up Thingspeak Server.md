## Setting Up ThingSpeak Server

[ThingSpeak](https://thingspeak.com) is an **IoT analytics platform** that allows you to **aggregate, visualize, and analyze live data streams** in the cloud.  
You can send data to ThingSpeak from your IoT devices, create real-time visualizations, and even set up automatic alerts and MATLAB-based analytics.

---

### Steps to Set Up ThingSpeak Dashboard

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

# NRF24L01-Based-STM32-Sensor-Node-with-ESP32-Gateway-Integration

This project demonstrates how to monitor sensor data wirelessly using an NRF24L01-based STM32 Sensor Node and an ESP32 Wi-Fi Gateway.
The system collects environmental data from the sensor node and uploads it to the ThingSpeak Cloud Server for real-time monitoring.

## Hardwar Requirement
- ESP32 Board
- STM32 Microcontroller	
- NRF24L01 PA+LNA
- BME280 Barometric Pressure Sensor	
-	Power Supply 5V	
-	Connecting Wires	
- Breadboard	
## Sensor Node Circuit

This project demonstrates a sensor node using an STM32F103C Bluepill microcontroller with an NRF24L01 module. Any sensor can be interfaced, but for this demo, a BME280 Barometric Pressure Sensor is used.

## WiFi Gateway Circuit

The gateway receives data from one or multiple sensor nodes via the NRF24L01 transceiver module. Once the data is received, it is uploaded to a server using a WiFi connection. The ESP32 combined with the NRF24L01 module is an ideal choice for building this WiFi gateway.

## Setting Up ThingSpeak Server

ThingSpeak is an IoT analytics platform that allows you to aggregate, visualize, and analyze live data streams in the cloud. You can send data from your devices, create real-time visualizations, and set up alerts.

### Steps to Set Up:

1. **Create an account** on [ThingSpeak](https://thingspeak.com).
2. **Create a new channel** to receive and display your data in graphical format.
3. **Fill in the channel parameters** as required (refer to the image below if needed).
4. Click **Save Channel** to finalize the setup.

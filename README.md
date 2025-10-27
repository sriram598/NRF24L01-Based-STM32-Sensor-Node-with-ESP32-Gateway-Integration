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
  
## IoT Sensor Node & WiFi Gateway

This project demonstrates an IoT system consisting of sensor nodes and a WiFi gateway:

- **Sensor Node Circuit:**  
  A sensor node uses an STM32F103C Bluepill microcontroller with an NRF24L01 module. Any sensor can be connected, but this demo uses a BME280 Barometric Pressure Sensor.

- **WiFi Gateway Circuit:**  
  The gateway receives data from one or multiple sensor nodes via the NRF24L01 transceiver module. After receiving the data, it uploads it to a server using a WiFi connection. The ESP32 combined with the NRF24L01 module is ideal for building this gateway.
  

## Setting Up ThingSpeak Server

ThingSpeak is an IoT analytics platform that allows you to aggregate, visualize, and analyze live data streams in the cloud. You can send data from your devices, create real-time visualizations, and set up alerts.


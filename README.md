# ENGO651_Lab5

## Overview
This project is an IoT Geoweb App developed for ENGO651 Lab 5. The app connects to an MQTT broker, publishes the user's current location and a random temperature as a GeoJSON message, and subscribes to a topic to receive and display similar messages on a map. The app uses the Paho MQTT JavaScript library for MQTT communication and Leaflet.js for mapping.

## Features
- **Connect/Disconnect:** Connect to an MQTT broker using the "Start" button and disconnect using the "End" button.
- **Auto-Reconnect:** Automatically reconnects to the broker if the connection is lost.
- **Share My Status:** Publishes a GeoJSON message with the user's current location and a random temperature (-40°C to 60°C) to the topic ENGO651/sherry_chalotra/my_temperature.
- **Receive Messages:** Subscribes to the same topic and updates the map with received GeoJSON messages, displaying a marker with a color based on the temperature (blue for <10°C, green for 10°C to 30°C, red for >30°C).
- **Map Visualization:** Uses Leaflet.js to display the location on an OpenStreetMap base map with a marker and a popup showing the temperature.

## Live Demo
The app is hosted on GitHub Pages: https://sherrychalotra03.github.io/ENGO651_Lab5/ 

## Setup Instructions
### Prerequisites
- A modern web browser (e.g., Chrome, Firefox, Safari) with WebSocket support.
- Access to the internet to connect to the MQTT broker and load external libraries.
- Geolocation enabled in your browser (for the "Share My Status" feature).
- MQTTX installed on your computer to test publishing and subscribing to MQTT messages.

### Installation
- Clone the Repository
- **Run Locally (Optional):** Use a simple HTTP Server using python -m http.server 8000 and open the browser and go to http://localhost:8000
- **Use the Live Demo:** Access the app directly via the GitHub Pages URL: https://sherrychalotra03.github.io/ENGO651_Lab5/.

### Usage
### Running the App
- Open the app in your browser using the GitHub Pages URL (preferred) or locally.
- **Connect to the MQTT Broker:**
  - The app is preconfigured to connect to broker.emqx.io on port 8084 using wss:// (secure WebSocket).
  - Click the "Start" button to connect.
  - The status will update to "Connected to broker.emqx.io\nSubscribed to ENGO551/sherry_chalotra/my_temperature".

### Share Your Status:
- Click the "Share My Status" button to publish your current location and a random temperature as a GeoJSON message.
- The map will update with a marker at the current location, colored based on the temperature (blue for <10°C, green for 10°C to 30°C, red for >30°C), and a popup showing the temperature.
- The status will update to "Status shared".

### Receive Messages:
- The app subscribes to the topic ENGO651/sherry_chalotra/my_temperature.
- When a message is received, the map updates with the new location and temperature, and the status updates to "Message received and map updated".

### Disconnect:
- Click the "End" button to disconnect from the broker.
- The status will update to "Disconnected".

## Testing with MQTTX
To test publishing and subscribing, use MQTTX to connect to the same broker and topic.

### Set Up MQTTX:
- Open MQTTX and create a new connection:
  - **Name:** Any name (e.g., "testnew")
  - **Host:** broker.emqx.io
  - **Port:** 8084
  - **Protocol:** wss (WebSocket Secure)
  - **SSL/TLS:** Check the box
  - **Username/Password:** Leave empty (anonymous access)
- Click "Connect". A green dot indicates a successful connection.

### Subscribe to the Topic:
- In MQTTX, enter the topic ENGO651/sherry_chalotra/my_temperature.
- Click the "Subscribe" button.

### Publish from the App:
- In the app, click "Start" to connect, then click "Share My Status".
- Check MQTTX— to see a GeoJSON message like:
![image](https://github.com/user-attachments/assets/989dc38a-0f03-4712-9cfd-4f2a2f2c21c7)
- Click the "Publish" button.
- Check the app—the map should update with a green marker at the coordinates, and the status should show "Message received and map updated".

## Project Structure
- **index.html:** The main HTML file containing the app’s structure.
- **styles.css:** CSS file for styling the app.
- **script.js:** JavaScript file containing the app’s logic, including MQTT connection, publishing, subscribing, and map updates.
- **README.md:** This file provides an overview and instructions.

## Technologies Used
- **HTML/CSS/JavaScript:** For the front-end structure, styling, and logic.
- **Paho MQTT JavaScript Library:** For MQTT communication (version 1.0.1).
- **Leaflet.js:** For map visualization (version 1.9.4).
- **OpenStreetMap:** As the base map for Leaflet.
- **MQTT Broker:** broker.emqx.io (public MQTT broker).
- **MQTTX:** For testing MQTT publishing and subscribing.

# ENGO651_Lab5

## Overview
This project is an IoT Geoweb App developed for ENGO651 Lab 5. The app connects to an MQTT broker, publishes the user's current location and a random temperature as a GeoJSON message, and subscribes to a topic to receive and display similar messages on a map. The app uses the Paho MQTT JavaScript library for MQTT communication and Leaflet.js for mapping.

## Features
- **Connect/Disconnect:** Connect to an MQTT broker using the "Start" button and disconnect using the "End" button.
- **Auto-Reconnect:** Automatically reconnects to the broker if the connection is lost.
- **Share My Status:** Publishes a GeoJSON message with the user's current location (via Geolocation API) and a random temperature (-40°C to 60°C) to the topic ENGO651/sherry_chalotra/my_temperature.
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

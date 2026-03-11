# SMART-LIGHT-CONTROL

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*: M NIKHIL KISHORE

*INTERN ID*: CT08DG1615

*DOMAIN: INTERNET OF THINGS

*DURATION*: 4 WEEEKS

*MENTOR*: NEELA SANTOSH

##The Smart Light Control project is a basic prototype that demonstrates how a smart lighting interface can be built using only front-end technologies. Developed entirely in Visual Studio Code, this project uses HTML and embedded JavaScript to create a simple, user-friendly web interface that simulates the remote control of a light—typically represented by an LED. The project does not include any backend programming or physical hardware connection; instead, it serves as a conceptual model of how a user might interact with a smart home lighting system through a browser.The core of the project is a clean and responsive web page containing two interactive buttons: “Turn ON” and “Turn OFF.” These buttons are styled using basic CSS for visual clarity and accessibility on mobile devices. When a user clicks either button, a JavaScript function is triggered, sending an HTTP request using the fetch() API to a URL such as /light?state=on or /light?state=off. Although no server or hardware is actively processing these requests in this version, the structure simulates how such commands would typically be sent to an IoT device, such as a Wi-Fi-enabled microcontroller (like ESP8266 or ESP32) in a real-world application.This HTML-only version is particularly useful for design validation, frontend development practice, and demonstrating how IoT systems can be visually controlled. It represents the first step in a larger smart home or automation system, where the interface is separated from the device logic. The use of Visual Studio Code provided an efficient and professional environment for writing, organizing, and previewing the HTML and JavaScript code. Its features, such as real-time code suggestions, syntax highlighting, and live preview extensions, made development faster and more accurate.The project has practical relevance in today’s world where smart homes and IoT systems are becoming increasingly common. Even without a backend or physical LED, the project helps build a strong understanding of how user interactions on a web page can translate into control commands. In real use cases, these HTML buttons would communicate with a server or microcontroller, which would then perform actions such as switching a relay or turning on an actual LED.Overall, this project is a simple yet meaningful demonstration of how HTML and JavaScript can be used to create functional, interactive user interfaces for smart devices. It highlights the role of frontend technologies in IoT systems and lays the groundwork for integrating backend logic and hardware in the future. The choice to use only HTML in Visual Studio Code keeps the project lightweight, platform-independent, and easy to deploy across different browsers and devices. This makes it a great starting point for students, interns, and hobbyists exploring smart control systems and web-based automation.

# Smart Lighting Control

## Overview

This project aims to simplify the control of various types of lighting through a smart lighting control system. It utilizes a web application that enables remote management of smart lighting via the internet.

The project consists of three main components:

1. **Control Side**: This is a web application built using HTML and JavaScript.

2. **Execution Side**: The execution side involves a NodeMCU ESP12f equipped with a light-dependent resistor (light sensor) and an LED lamp. The LED lamp serves as a representation of the lighting.

3. **Real-time Database**: The project utilizes Google's Firebase service to create a real-time database that facilitates communication between the control and execution sides.

## Functionality

The system offers the following functionalities:

### Automatic Lighting Control

- Users can set the desired level of room illumination using a slider on the web application.
- The web application communicates the selected illumination level to the real-time database.
- The execution side regularly checks this value and automatically turns the lighting on or off based on the user's threshold.

### Manual Lighting Control

- Users have the option to manually control the lighting.
- The web application provides buttons to enable or disable automatic lighting control.
- When automatic control is disabled, the slider for setting the illumination threshold in automatic mode is deactivated, and a manual slider for adjusting the illumination level is activated. Users can use this slider to increase or decrease the current light level.

### Sensor Data Display

- The web application displays real-time sensor data, showing the current value of the light sensor measuring the room's illumination.
- These sensor values are refreshed every 5 seconds.

## Usage

To use this project, follow these steps:

1. **Firebase Configuration:**
    - Set up a Firebase project at [Firebase Console](https://console.firebase.google.com/).
    - Create a real-time database in Firebase.
    - After setting up Firebase, obtain the following information from your Firebase project:
        - Firebase project API Key
        - RTDB URL (Real-Time Database URL)

    If you prefer, you can use my pre-made Firebase project by clicking [here](https://console.firebase.google.com/u/0/project/iot-seminarski-d5dbe/database/iot-seminarski-d5dbe-default-rtdb/data).

2. **Arduino Project Setup:**
    - Set up the NodeMCU ESP12f with the necessary components (light-dependent resistor and LED lamp).
    - Open the Arduino project located in the `Smart-Lighting/arduino/Pametna rasvjeta` directory.
    - Ensure you have the Arduino IDE installed.
    - Connect your NodeMCU ESP12f to your computer.
    - Before uploading the Arduino sketch (`Pametna rasvjeta.ino`) to the NodeMCU ESP12f, make the following changes in the code:

        ```cpp
        // Insert your network credentials
        #define WIFI_SSID "your_wifi_name"
        #define WIFI_PASSWORD "your_wifi_password"

        // Insert Firebase project API Key
        #define API_KEY "your_firebase_api_key"

        // Insert RTDB URL (define the RTDB URL)
        #define DATABASE_URL "your_firebase_database_url"
        ```

    - Upload the modified Arduino sketch to the NodeMCU ESP12f.

4. **HTML Page:**
    - Open the `Smart-Lighting/index.html` file in your preferred web browser.
    - Update the Firebase configuration in the HTML file by modifying the following section:

        ```javascript
        const firebaseConfig = {
          apiKey: "your_api_key",
          authDomain: "your_auth_domain",
          databaseURL: "your_database_url",
          projectId: "your_project_id",
          storageBucket: "your_storage_bucket",
          messagingSenderId: "your_messaging_sender_id",
          appId: "your_app_id",
        };
        ```

**Note**: Please ensure that you have the required hardware components and understand how to set up and configure the NodeMCU ESP12f and Firebase before using this project.

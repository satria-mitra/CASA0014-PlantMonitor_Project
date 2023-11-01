# Plant Monitor project
This repository is CASA0014 Connected Environment project for plant monitor, workshop no.2

# Overview
This project is based on Plant Monitor that could monitor a plant conditions such as temperature, humidity and soil mosture, send this data to MQTT CE server via wifi and display live data via webserver and from Grafana. 
I add another function to display those parameters to OLED Display and also add a function to display message from a subscribed topic so I can communicate with my plant.

## Prerequisites

Before using this code, make sure you have the following prerequisites:

- An ESP8266 microcontroller.
- DHT 22 sensor
- Two nails and two cables as soil mosture sensors
- Two pieces of 10K Ohm resistors
- A 200K Ohm resistor and a 100 Ohm resistors
- Breadboard for prototyping
- Libraries installed for ESP8266, MQTT, and OLED display (see below)
- Sensitive data (such as Wi-Fi network credentials and MQTT server details) and in a file named `arduino_secrets.h`.
- [Plant Monitor project from Duncan Wilson](https://github.com/ucl-casa-ce/casa0014/tree/main/plantMonitor) for the original idea

## Libraries Used

The code includes the following libraries:

- [ESP8266WiFi](https://github.com/esp8266/Arduino): For ESP8266 Wi-Fi functionality.
- [PubSubClient](https://pubsubclient.knolleary.net): For MQTT communication.
- [ssd1306.h](https://www.arduino.cc/reference/en/libraries/ssd1306/): For controlling an OLED display.



## Feature added explanation

Apart from [cool plant monitor](https://github.com/ucl-casa-ce/casa0014/tree/main/plantMonitor) project by Duncan , I add some features to display the messages sent to MQTT CE server and display a subscribed topic to OLED Display. This could be done by adding a function and little modification to the original projects. The upgrade explained below

### subscribeToTopic functions

The `subscribeToTopic()` function is executed to display messages from a certain topic which we subscribed. This function would display the message to serial monitor for debugging purpose


## Building process

The original project was built using Plant Monitor Shield V2 from [Plant Monitor](https://github.com/ucl-casa-ce/casa0014/tree/main/plantMonitor) and mainly built during CE Wokrshop in the class. To add LCD display, I use a breadboard for prototyping. 

![Prototyping process](https://github.com/satria-mitra/Plant-Monitor/blob/main/assets/prototyping_process.jpg)

Image: Prototyping process with LCD added

### Schematis and paper design
Started with thinking of what features that I want to add to plant monitor, I ended up with adding OLED Display to the original projects. Apart from DTH 22, soil mosture sensors and voltage divider circuit, I added schematics for OLED Display. The sketch below shows the design of the circuit :


![Schematics](https://github.com/satria-mitra/Plant-Monitor/blob/main/assets/schematiscs.jpg)

Image: Schematics on paper, red dotted line shows original project, blue dotted line shows additional OLED Display 


## Future Improvement

I also want to implement improvement in the future if I have a chance to upgrade this project. Some cool features that came into my mind were :

- Playing a sound from subscribed messages using [Talki library] (https://www.arduinolibraries.info/libraries/talkie)
- [Sonification project](https://www.instructables.com/Biodata-Sonification/) using sound to illustrate how a Plant could singing :)
- [RGB Audio visualizer](https://projecthub.arduino.cc/janux/rgb-32-band-audio-spectrum-visualizer-2f4788) also would be a perfect companion for that sonification idea


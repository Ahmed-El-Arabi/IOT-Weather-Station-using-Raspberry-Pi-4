# IOT Weather Station using RPi4
## 1. Introduction


Weather and climate play significant roles in human life, and monitoring environmental parameters such as temperature, humidity, and rainfall is essential for safety and building control. Sensors are crucial components in measuring environmental parameters, and with the advent of the Internet of Things (IoT), these sensors can be interconnected to physical devices, buildings, and vehicles. This semester, our project involves building a Raspberry Pi-based Weather Station using multiple sensors to measure temperature, humidity, and rainfall. The DHT22 and FC-37 sensors are used to measure temperature and humidity and rain detection, respectively. The project aims to display real-time humidity, temperature, and rainfall data on an internet server through a ThingSpeak server. Additionally, an acknowledgment email is sent when the data is received.

![Schematic](https://user-images.githubusercontent.com/96639538/229324359-75b163ef-ff5d-45dc-bb75-927507da54fc.png)

![Schematic](https://user-images.githubusercontent.com/96639538/229324400-a44b304c-f540-4528-b028-ed3e684254a9.png)

![image](https://user-images.githubusercontent.com/96639538/229324369-aec9f6de-ca6e-47ca-80d3-bb0cbeb87183.png)

![Block Diagram for overall system](https://user-images.githubusercontent.com/96639538/229324376-6dfaee49-038d-4b12-b1c2-d8eda48cba6d.png)


## 2. Hardware components included

### 2.1 Development board (Raspberry Pi 4):

The Raspberry Pi is a compact Linux computer development board with five different variations. The Raspberry Pi 4 Model B is the latest board, featuring a quad-core 64-bit Broadcom 2711 Cortex A72 processor clocked at 1.5GHz. This model was released in June 2019 and is used as the main development board for the proposed weather forecasting system.

![Raspberry PI model 4](https://user-images.githubusercontent.com/96639538/229324410-824789f7-fe36-417e-968f-83ea4b3bf0dc.png)

### 2.2 DHT22Temperature & Humidity Sensor:

The first sensor to be installed will be the DHT22 for capturing air temperature and relative humidity data. The ADAFRUIT site provides great information about those sensors. 
Below, some information retrieved from there:


![image](https://user-images.githubusercontent.com/96639538/229324455-76997a2a-ba09-4ea8-99f6-1f4867950f59.png)

DHT temperature and humidity sensors are affordable and basic sensors that consist of a capacitive humidity sensor, a thermistor, and a chip that converts analog signals into digital signals. Although these sensors are slow, they are ideal for hobbyists who want to perform simple data logging and can be easily read using any microcontroller.

### 2.3 FC37 Rain Detector Sensor:

The rain sensor is used to detect water and it can detect beyond of what a humidity sensor do. It will display “It’s raining” when it detects water, which is in our case is rain.
It has a built-in potentiometer for sensitivity adjustment of the digital output (D0). It also has a power LED that lights up when the sensor is turned on and a digital output LED.
Basically, the resistance of the collector board varies accordingly to the amount of water on its surface.

![image](https://user-images.githubusercontent.com/96639538/229325006-1f6d068a-2fc7-44ff-aa3d-35f5f6dfeff4.png)

When the board is:
- Wet: the resistance increases, and the output voltage decreases
-	Dry: the resistance is lower, and the output voltage is higher

![image](https://user-images.githubusercontent.com/96639538/229325014-7ff51d63-db7a-4072-964b-19f29f976041.png)

## 3. Software used

1. Thonny IDE: which is integrated development environment for Python that is designed for beginners. It supports different ways of stepping through the code, step-by-step expression evaluation, detailed visualization of the call stack and a mode for explaining the concepts of references and heap. (Programming Language: Python) 
2. Thingspeak (‘Collects’ the data from the sensors, ‘Analyse and Visualize’ the data and ‘Acts’ by triggering a reaction)


## 4. Function Specifications

This IoT based Project aims to show the current Humidity, Temperature and Rain detection parameters on the Internet server using Raspberry Pi, which makes it a Raspberry Pi Weather Station. 
Firstly DHT22 sensor senses the Humidity & Temperature Data and Fc37 sensor which detects rain. 
Secondly Raspberry Pi reads the DHT22 sensor module’s output by using single wire protocol and rain detection sensor and extracts both sensors values into a suitable number in percentage (humidity), Celsius scale (temperature), High or Low detection of rain (rain detection). 
Thirdly, these values are sent to ThingSpeak server by using inbuilt Wi-Fi of Raspberry Pi 4 and also an email is sent to the receiver’s email acknowledging the data values from both sensors.
Finally ThingSpeak analyses the data and shows it in a Graph form and an email is sent which displays the data numerically.


## 5. Protocols applications:

The data collected from the sensors is saved locally using a loop function, and an IoT platform, ThingSpeak, is used to send the data over the internet. ThingSpeak is an open-source IoT application that enables the creation of sensor logging and location tracking applications. An MQTT protocol is used to connect to the ThingSpeak broker, which enables messages to be pushed to client devices without the device continuously polling the server. MQTT over WebSockets can be secured with SSL. ThingSpeak has an MQTT broker that supports both MQTT publish and MQTT subscribe, and in this case, MQTT Publish is used to send data to the broker.

![image](https://user-images.githubusercontent.com/96639538/229325179-78ab5b8b-a31d-4454-89d5-043c5238cd91.png)

This passage explains the SMTP protocol, which is used by mail servers to send, receive, and relay outgoing mail between email senders and receivers. It also mentions that an SMTP email server will have an address that can be set by the mail client or application being used. Examples of SMTP servers are provided, such as Gmail and AOL. The process of sending an email with SMTP is also briefly described.

![image](https://user-images.githubusercontent.com/96639538/229325208-ae03f85c-90c4-4b1a-bee4-3498d71798f4.png)

![image](https://user-images.githubusercontent.com/96639538/229325212-ef9e4075-4747-4204-8cd0-46f5a5de7bb0.png)


## Visualizations of actual live data sent successfully using our 2 communication protocols:

![Data sent to our channel on the website](https://user-images.githubusercontent.com/96639538/229325278-877b3019-b83b-484e-8676-f5d6e2f0f254.png)

![Accessing the channel on mobile App](https://user-images.githubusercontent.com/96639538/229325282-81f95b59-a1c8-4ecd-ac9c-e531e2654984.png)

## These are the acknowledgment emails for both sensors

Note: The email of my teammate was the one used at the time

![image](https://user-images.githubusercontent.com/96639538/229325346-5c308c79-6003-4536-b50e-e6d1fbc8152d.png)

![image](https://user-images.githubusercontent.com/96639538/229325347-6b40be6a-9a7c-45c5-a434-a0fdbd533c77.png)



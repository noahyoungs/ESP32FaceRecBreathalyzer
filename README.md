# ESP32 FaceRec Breathalyzer
ESP32 Based Facial Detection and Alcohol Breathalyzer TIme Clock

This library implements a Time Clock device which uses the ESP32-Cam development board and an MQ3 alcohol sensor to log a timestamp and breath alcohol level to a server. It is a prototype for a time clock device that can be used by employers to check their employees breath alcohol level when they clock in. 

How to install:
Take the components of the ESP32 folder and open them in arduino IDE. In CameraWebServerWorking.ino, Uncomment the definition for the development board you are using, and change the ssid and password to your wifi details. In app_httpd.cpp, change the variable serverName to include the ip address to your server, as well as the pin number where the analog input of the MQ3 sensor is connected.  Install the included libraries. Make sure PSRam is enabled and use the Huge App partition scheme to flash the esp32. 

Make sure node’s and npm are installed on your server. Upload the components of the server folder to your server and run npm install. Then use nodejs to run server.js

How to use:
Find the ip address of the esp32 through the serial connection to the esp32. Go to this ip address in your web browser. Enable face recognition and face detection using the web UI. Use the enroll face button to enroll 5 faces per user. Once the faces are recognized, the LED will flash once, and the user has 5 seconds to blow into the MQ3 sensor. Then, the LED will flash again, and an ID representing the recognized face and the sensor value will be sent to the server via HTTP request. 



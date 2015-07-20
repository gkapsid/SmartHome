# SmartHome
Smart home documentation and files

This file contains info about the smart home project I implemented.
The project includes:
An app for android device
Software for the arduino Leonardo + Ethernet shield
Schematics for the required hardware

## The Android App
The application for the android device is used for three purposes:

1. To control two external devices (electrical appliances like light, coffee machine etc.).
2. To get a measurement from a sensor, that for the moment is a thermometer.
3. To activate a camera

The app is based on code found in:
http://www.greeceandroid.gr/dev/671-smart-home-android-arduino-12
The environment used for the code development was the ECLIPSE Platform
The code was in some point old so the complete updated code can be found in the file SmartHome   


### Assets
There are a few assets that are used in the Android app like images and some jQuery mobile related files. 
There is also a folder called "content" which contains the html file which is the app's environment. 
### The Android App's code
The app creates a custom web browser where a local html file is loaded. The html file is a list where the user chooses whether to set on/off an appliance, to view the value of a sensor or to activate a camera.
In the html file that is in assets/content folder the developer has to declare the ip addresses of the arduino server and the camera servers.

The camera servers are implemented using an IP camera or the appropriate software if the camera is a smart phone. The one used in the project I implemented is IP webcam found in https://play.google.com/store/apps/details?id=com.pas.webcam . 

### Special points for Android code
### The Arduino code 


### The camera
### Arduino relays
### Future improvements

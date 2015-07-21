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
The code was in some point old so the complete updated code can be found in the file **SmartHome**   


### Assets
There are a few assets that are used in the Android app like images and some jQuery mobile related files. 
There is also a folder called "content" which contains the html file which is the app's environment.
The assets can be found in http://www.greeceandroid.gr/images/articles/development/smart-home-android-arduino-12/assets.zip and an updated version in the **assets.zip** file.

### The Android App's code
The app creates a custom web browser where a local html file is loaded. The html file is a list where the user chooses whether to set on/off an appliance, to view the value of a sensor or to activate a camera.
In the html file that is in assets/content folder the developer has to declare the ip addresses of the arduino server and the camera servers.

The camera servers are implemented using an IP camera or the appropriate software if the camera is a smart phone. The one used in the project I implemented is IP webcam found in https://play.google.com/store/apps/details?id=com.pas.webcam . 

### Special points for Android code
### The Arduino code 
The base Arduino code was found in Examples --> Ethernet --> WebServer and in addition in the 
http://www.greeceandroid.gr/images/articles/development/smart-home-android-arduino-8/part8/part8.txt
In my case thought (Arduino Leonardo and Arduino 1.6.4 software) failed to use the Webserver.h library. 
The sketch failed to be compiled. It seemed to stuck for ever in a certain point.
So the sketch was redesigned without the use of the certain library.
The solution that was implemented found (partially) in the 
http://www.instructables.com/id/Arduino-Webserver-Control-Lights-Relays-Servos-etc/

Then the sketch was modified to accomodate instead of the two buttons (on/off) one slider and a temperature value from a thermometer. All the above was wrapped in a list.

The final sketch incorporates two sliders for two devices and a sensor (file **ArduinoCodeFinal**).

### The camera
### Arduino relays
### Future improvements

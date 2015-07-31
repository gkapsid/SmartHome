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
To reach a device from internet two things are necessary:

1. A static IP for each server on the internal network. To each server a port will be assigned through port forwarding.
2. A dynamic DNS service has to be used because typically a domestic internet conection uses dynamic (not static ) IP.

Here one web server is the Arduino (through Ethernet or WiFi shield) and each camera that will be used.



### Assets
There are a few assets that are used in the Android app like images and some jQuery mobile related files. 
There is also a folder called "content" which contains the html file which is the app's environment.
The assets can be found in http://www.greeceandroid.gr/images/articles/development/smart-home-android-arduino-12/assets.zip and an updated version in the **assets.zip** file.

### The Android App's code
The app creates a custom web browser where a local html file is loaded. The html file is a list where the user chooses whether to set on/off an appliance, to view the value of a sensor or to activate a camera.
In the html file that is in assets/content folder the developer has to declare the ip addresses of the arduino server and the camera servers.

The camera servers are implemented using an IP camera or the appropriate software if the camera is a smart phone. The one used in the project I implemented is IP webcam found in https://play.google.com/store/apps/details?id=com.pas.webcam . 

### Special points for Android code
For the **Webview** to work properly must register in AndroidManifest.xml a tag as follows:

<uses-permission android:name="android.permission.INTERNET"/>

this is done: 

1. Open AndroidManifest
2. Go to tab “Permissions”
3. Select “Add…”
4. Select “Uses-permission”
5. Select from a dropdown menu on the right "android.permission.INTERNET" 
6. and save

source: http://developer.android.com/guide/webapps/webview.html

To create more than one pages in **one** html file use: 
data-role="page" id="sensor”

To show straight a specific page I should write: 
ddns.address:portnumber/#pagename
eg
in a file amine.html there are two pages
id = “main”  
id = “cam”
if I write
"http://localhost/android/amine.html" the browser shows the page "main"
but if I write "http://localhost/android/amine.html#cam" it shows straight the page cam


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
The camera can be any IP camera or an old smartphone. The smartphone needs to operate as server with static IP. 

To view the camera from outside the local network, port forwarding, for each camera, is needed.
### Arduino relays
Arduino can drive loads where the current doesn't exceed 40 mA for each output pin. To avoid problems with the relays usually a typical driver circuit is used. This can be found in file **relay_drive_circuit.png**.

### Future improvements
when the user closes and opens the app again, doesn't know if each connected divice is on or off. This is going to be implemented in the next version of the project.

A better interface may be implemented using a SD card. This is going to be studied in due time.


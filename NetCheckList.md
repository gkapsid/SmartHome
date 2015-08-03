**A check list for the home network setting.**

* Collect Dynamic DNS data (site, password, anything else necessary)
* Set the router and check it.
* Port forward the Arduino web server
* The assigned port is defined in arduino code (EthernetServer server(xxxx);).
* The whole address (ddns and port) is declared in the html file found in assets/content.

If it is not necessary to have access from outside, but only within the LAN, then the web server can be accessed 
using only the static IP.

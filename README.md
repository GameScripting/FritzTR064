# FritzTR064

Java-library to communicate with the AVM FritzBox by using the TR-064 protocol.

## Installation

Use Jitpack:
https://jitpack.io/#GameScripting/FritzTR064/

    compile 'com.github.GameScripting:FritzTR064:v1.0'


## Dependencies

This library depends on:

* [HttpClient 4.x](https://hc.apache.org/httpcomponents-client-4.4.x/logging.html)

## Quickstart

Get all the posibel Actions:

```java
FritzConnection fc = new FritzConnection("192.168.1.1","<username>","<password>");
fc.init();
fc.printInfo();
```
The next Example shows how you can get the number of connected Wlan Devices:
```java
FritzConnection fc = new FritzConnection("192.168.1.1","<username>","<password>");
fc.init();
Service service = fc.getService("WLANConfiguration:1");
Action action = service.getAction("GetTotalAssociations");
Response response = action.execute();
int deviceCount = response.getValueAsInteger("NewTotalAssociations");

```
For more examples see: [The Example Folder](https://github.com/mirthas/FritzTR064/tree/master/examples)

## Resorces
* [AVM API Description](http://avm.de/service/schnittstellen/) (German)
* [Examples](https://github.com/mirthas/FritzTR064/tree/master/examples)

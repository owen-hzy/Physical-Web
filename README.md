## Introduction

This repository contains building block for [physical web](https://google.github.io/physical-web/) demonstration.

## Components
* TI CC2540 BLE experiment board
* Arduino YUN

## Description

The project consists of three parts:

1. Bluetooth CC2540 broadcasts [Eddystone](https://github.com/google/eddystone) advertisement packet which contains web application URL. The related implementation is in folder **BLE**.
2. ArduinoYUN connects to a server using library autobahn which implements [WAMP](http://wamp-proto.org/). Basically, the *serial\_to\_wamp.js* file just registers callback functions to server waiting to be invoked by client. It also publishes data waiting to be subscribed. The **StandardFirmataYUN** is the MCU part of ArduinoYUN which bridges the MCU and linux part on ArduinoYUN. The related implementation is in folder **ArduinoYUN**.
3. Web application which connects to server using WAMP invokes the function registered and subsribes to the topic which ArduinoYUN publishes. The related implementation can be found in folder **Web**.

The demo can be found [here](http://v.youku.com/v_show/id_XMTU2OTk0ODk1Ng==.html?from=y1.7-1.2).
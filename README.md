# node-red-obniz-neopixel-matrix-test #

just a few Node-RED flows to test a Neopixel matrix connected to an obniz board

This repository contains a few simple [Node-RED](https://nodered.org/) flows to control an [obniz board](https://obniz.com/products/obnizboard) with an attached Neopixel 16x16 RGB matrix - but they may easily be adapted to other geometries of chained WS2812 RGB LEDs (but only up to a length of 85 LEDs because of restrictions in the obniz board)

While the idea behind the obniz board has its benefits, the quality of software and documentation is...not really optimal - these flows may therefore perhaps help necomers to work with the board and attached WS2812 strings.

> Just a small note: if you like this work and plan to use it, consider "starring" this repository (you will find the "Star" button on the top right of this page), so that I know which of my repositories to take most care of.

## Prerequisites ##

In order to run these examples you will need

* a working Node-RED instance,
* [node-red-contrib-obniz](https://flows.nodered.org/node/node-red-contrib-obniz) - which installs some nodes to communicate with obniz boards,
* an obniz board,
* Internet access (because of the obniz board) and
* any kind of WS2812 RGB LED or string

## Instructions ##

Once you have all the components together, you will have to

* start up (and configure) the obniz board
* connect the WS2812 LED string
* import these flows
* configure the obniz nodes (i.e., enter the credentials of your board) and
* start the flows as desired

![](flows.png)

## License ##

[MIT License](LICENSE.md)

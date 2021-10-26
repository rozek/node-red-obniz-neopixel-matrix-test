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

### Start-up the Obniz Board ###

After powering up the obniz board, you will have set-up a Wifi connection (as desribed in the board's instruction manual) and - once the board has established a connection to its server - configure board access in the [obniz developer's console](https://obniz.com/console/devices): simply

* press "+ Add device"
* choose your board type
* press "I'm ready" and
* type in your obniz id and press "Next"

### Connect the WS2812 LED String ###

In this example, the WS2812 "data in" wire is connected to pin 4 of the obniz board. If you prefer a different pin, you may do so by modifying the "obniz function" nodes accordingly.

The LED's Vcc and GND wires should be directly connected to your power supply.
 
### Import the Flows from this Repo ###

If not already done, you should install the obniz nodes from [node-red-contrib-obniz](https://flows.nodered.org/node/node-red-contrib-obniz) as described on that page.

Now, you may import the [flows](https://raw.githubusercontent.com/rozek/node-red-obniz-neopixel-matrix-test/main/flows.json) from this repository. Just select the whole text, copy it into the clipboard, then choose "Import" from the Node_RED Editor menu, copy the clipboard contents, press "Import" and drag the flows to a place of your choice.

### Configure Obniz Nodes ###

Once the flows have been imported, the obniz nodes have to be configured: you have to provide the serial id of your board and the access key you generated in the [obniz developers console](https://obniz.com/console/devices). "Instructions" can be found on the [obniz node page](https://flows.nodered.org/node/node-red-contrib-obniz) - as usual, there are in a horrible shape, but fortunately, it turns out not to be too difficult

### Run desired Flows ###

This repository contains four different flows. Because of how the obniz board works, they have to share the configured wiring - once set up, it will be stored in the flow context and reused by any other flow (which is why it has to be reset automatically upon re-deployment)

* **x-axis**<br>this flow draws a "x-axis" by lighting the LEDs 0, 1, 2 up to 15
* **y-axis**<br>this flow draws a "y-axis" by lighting the LEDs 0, 16, 32 and so on - this is useful because matrices are usually wired in a serpentine manner
* **test of 5 rows**<br>the initial idea was to write a short function test to see if all matrix LEDs work as intended. This flow tests 5 rows of the connected matrix (because of restrictions in the obniz board) row-wise and alternately in red, green and blue
* **clear matrix**<br>WS2812 LEDs are very bright and may disturb when lighting - this flow therefore switches all LEDs off

## License ##

[MIT License](LICENSE.md)

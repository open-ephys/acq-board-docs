.. _peripheraldevices:
.. role:: raw-html-m2r(raw)
   :format: html

Peripheral devices
=================================================

Open Ephys I/O Board
#########################

Need to sync your neural data with external triggers? Use an I/O board to connect up to 8 digital inputs to the acquisition board. Since its internal components are completely passive, the I/O board can be also be used to relay digital outputs, analog inputs, and analog outputs.

Instructions on where to plug things in

HDMI cables are not real HDMI ports!

2do: add note on jumper positions for configuring straight to AD/buffer op-amo/ voltage divider

Specifications

* 8 vertical BNC terminals

* HDMI type A connector

* 4.9" x 3.6" PCB

If you're interested in building your own I/O Board, follow the instructions :ref:`here <assemblingtheioboard>`.

HDMI Breakout Boards
####################

There are also a variety of simple HDMI breakout boards available from various vendors - these work equivalently as I/O boards. See for instance `here <https://elabbay.myshopify.com/collections/breadboard/products/elabguy-hdmi-af-bo-v1a-hdmi-type-a-female-socket-breakout-board>`__.

HMDI channel mapping
1	DATA2+
2	DATA2–
3	DATA1+
4	DATA1–
5	DATA0+
6	DATA0–
7	CLOCK+
8	CLOCK–

Changing the Analog Input Range
################################

The default setting is to have the ADCs run from -5 to +5V, although in practice the actual range is ±4.5V (up through Acquisition Board version 2.2). If you need to go up to 5V, the ADC must be switched to 0-5V mode.

To switch the ADC range, open up the case of the acquisition board and move the jumpers near the ADC input HDMI to the two pins farther away from the edge of the board. Different channels can have different jumper settings, but make sure you record which is which! There's no way for the software to know the setting for each channel. Channel 1 is the rightmost jumper (closer to the headstage inputs), Channel 8 is the leftmost jumper.



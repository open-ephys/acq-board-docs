.. _usermanual:
.. role:: raw-html-m2r(raw)
   :format: html

User Manual
=================================================

If you already have these components, follow the :ref:`quickstartguide` to learn how to start collecting data right away.

This page provides more details about the acquisition board specifications and how it works.

The focus of this page should be what's going on "under the hood" of the acquisition board, rather than how the end user should interact with it. Even so, we recommend reading this page carefully if you're going to use our hardware, and especially if you're going to build it. When something goes wrong, or if your data look suspicious, knowing the basics of how the hardware works will make it easier to troubleshoot. And the more people who have a thorough understanding of the Open Ephys ecosystem, the easier it will be to support new users.

We're going to assume a basic understanding of electronic circuits, but this is by no means advanced stuff. If you don't have any hands-on experience working with electronics, it might be a good idea to start with some of the tutorials on SparkFun or Adafruit. Keep in mind that this is how the co-founders started out around 2010, and now we can build ephys systems from the ground up. Fortunately we were able to use the Intan RHD2000 Evaluation Board as a reference, which made things a lot easier for us. For that reason, it would also be helpful to read through the documentation available on the Intan website, as almost everything related to the RHD2000 chips is relevant to our hardware.

Neural data acquisition
########################

The neural data acquisition in the system is fully handled by Intan's RHD chips. The chips contain 16 or 32 20x gain amplifiers and bandpass filters. During the amplification, the voltage is referenced to either a common REF input (RHD2132 and RHD2164 chips), or to a separate reference/negative input for each channel (RHD2216 chips). The voltage is the multiplexed in time at a speed of up to 30 kHz /channel for 32 channels, and digitized by an on-chip 16-bit ADC. From this point on, electrical noise will not degrade the signal, as long as the integrity of the digital signals is maintained.

The data is transmitted from the chip to the FPGA via a serial protocol that also handles configuration of the chip (mainly setting of the band-pass filters) and transmits some extra data such as temperature, supply voltage at the headstage, and in the case of many headstages, accelerometer data. The headstages are connected using standardized SPI cables using small omnetics connectors.

Opal Kelly FPGA
#################

The most important part of the acquisition board is the FPGA, or "Field-Programmable Gate Array." This amounts to about half the cost of an acquisition board, so it better do something crucial. From a high-level perspective, the FPGA takes data from everything that's connected to the acquisition board, attaches a timestamp, and sends it to the computer via USB. It effectively acts as a "dumb pipe," shuttling data between peripheral devices (such as headstages and I/O boards) and the computer, where the actual processing takes place. However, this doesn't even come close to taking advantage of all of its capabilities. An FPGA is sort of a cross between a microcontroller (like an Arduino) and a circuit composed of interconnected transistors. It can be reconfigured on the fly, but the modules that are uploaded all run in parallel, rather than being called consecutively inside a loop. That means the FPGA can be really fast and its timing can be very precise. This is essential for collecting data at 30 kHz per channel across each of an Intan chips 32 channels, which must be sampled one by one.

We chose to use the Opal Kelly XEM6010 development board because of the terrific programming interface provided by Opal Kelly. If we just soldered the bare FPGA (Xilinx Spartan 6) to our acquisition board, it would have driven down costs significantly, but would have required some serious programming chops to get it to play nicely with the computer. Since we're already at such a low price point, our most precious resource is time, rather than money. The XEM6010 has the added advantage of being footprint-compatible with a development board that uses PCI-express, rather than USB, so there's very little work involved in switching to a much faster data-transfer protocol.

The FPGA itself is programmed in a language called Verilog. Verilog is a type of "hardware description language," because it specifies the actions of registers and logic gates, rather than functions and variables. Verilog is compiled to a "bitfile," which must be uploaded to the FPGA each time it's used. Compiling the bitfile can take several minutes, but uploading it occurs almost instantaneously. The Verilog code that runs on the acquisition board FPGA is our custom version of the "Rhythm" interface developed by Intan. We had to change a few things in order to communicate with our analog-to-digital converters (we're using Texas Instruments ADCs, rather than Analog Devices) and control the 8 LEDs on the board. If you're interested, you can take a look at the source code here (not recommended unless you have some Verilog experience).

Analog Output
################

There are eight analog outputs on the board, which use the 16-bit DAC8531 chip from Texas Instruments. The DACs are controlled by the Rhythm interface. Analog output channels 1 and 2 can be set to monitor any of the headstage inputs through software. Any of the channels can be programmed to deliver custom waveforms as well, but this functionality hasn't been added to the GUI yet.

NOTE: The Intan RHD2000 Evaluation Board uses the AD5622 DACs from Analog Devices. The footprint is different, but the control commands are identical.

All analog and digital inputs&outputs use the same standardized pins on a standard HDMI cable, so you can use the same breakout boards and accessories for all of them.
DO NOT plug actual HDMI devices into the acquisition board, this will likely result in damage.

Analog Input
############

There are eight analog inputs on the board, which use the 16-bit ADC161S262 chip from Texas Instruments. 

There are three settings:

#. ±5V input sent through an op amp (jumper closer to the edge of the board)
#. 0-5V input directly from the HDMI connector (jumper farther from the edge of the board)
#. 0-5V input sent through an op amp (no jumper)

NOTE: The Intan RHD2000 Evaluation Board uses the AD7680 ADCs from Analog Devices. The control sequence for these chips is not directly compatible with the one used by the TI chips. Therefore, if you want to use the Open Ephys acquisition board with Intan's software (or Intan's board with the Open Ephys software), you'll have to exchange the default FPGA bitfile in order for the ADCs to work.

Digital Output
################

The acquisition board has eight 5V digital outputs connected to an HDMI connector. These interface with a level shifter (Texas Instruments SN74LVC4245A) to allow the 3.3V outputs of the FPGA to send 5V signals out of the board. There are eight additional outputs in the Rhythm firmware, which are connected to holes on the bottom of the board. The digital outputs are not yet part of the Open Ephys software.

Digital Input
##############

The acquisition board has eight 5V digital inputs connected to an HDMI connector. These interface with a level shifter (Texas Instruments SN74LVC4245A) to prevent 5V inputs from damaging the FPGA (which runs on a 3.3V supply). There are eight additional inputs in the Rhythm firmware, which are connected to holes on the bottom of the board.

Power Supply
###############

The acquisition board runs on a 5V DC power supply. DO NOT use any other type of power supply, as it could permanently damage the board.

Since consumer-grade wall socket power supplies tend to be rather noisy, we have our own 5V regulators on the board. There are a few other regulators for different functions, such as powering the headstages and creating a –5V rail for the op amps. Below is a schematic of all the voltage levels on the board. The main ones have test holes labeled on the bottom of the board, so you can check the voltage without opening up the case.

.. image:: ../_static/images/usermanual/powersupply.png
  :alt: Details of the internal voltages

Other Features
################

*LEDs:* The eight WS2812 LEDs can be controlled via a single digital line, and don't require any external parts except for a 0.1 µF bypass capacitor.

*BNC clock output:* We plan on using the BNC connector to send a signal each time the acquisition board takes a sample, but this hasn't been programmed yet. In the meantime, the connector is a great way to ground your board if you're running it off battery power! You would do this by connecting the outer shield of this connector (NOT the center pin) to an appropriate ground – a large metal rack, a piece of copper sunk deep into the wall, or even the ground plug of a 3-prong outlet.

*I2C bus:* Each of the four HDMI ports includes 2 channels that are connected to an I2C bus. This will provide a convenient way to expand the functionality of the acquisition board through custom I/O boards. However, the I2C functionality hasn't been added to the firmware yet.




.. toctree::
    :hidden:
    :maxdepth: 5
    :titlesonly:

    Quickstart-guide
    Electrodes
    Headstages
    Cables
    Peripheral-devices
    Computer-hardware
    Acquisition-software


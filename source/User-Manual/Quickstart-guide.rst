.. _quickstartguide:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Quickstart guide
***********************************

#. **Connecting the USB cable and power supply**

    *Required components: USB cable, 5V power supply*

    Connect the USB cable to a USB port on your computer. If possible, using a USB 3.0-compatible port is recommended (often indicated by a blue color). USB cables longer than 2 meters are not recommended.

    .. warning:: Make sure you're using a 5V DC power supply! The latest version of the Acquisition Board includes over-voltage protection, but it's always safest to use the power jack on the Acquisition Board. Do not use the power supply on the FPGA, next to the USB port. The acquisition board power jack has extra protections to avoid damage to the system that the FPGA plug lacks.

    .. image:: ../_static/images/usermanual/quickstart/power_usb.jpg
      :width: 70%
      :align: center

#. **Connecting the headstages**

    *Required components: RHD headstage, SPI cables*

    There are four headstage connectors on the front of the acquisition board. You can use any combination of the four (but you might as well start with input "A"). The connectors on the SPI cables are very small, so sometimes they can be tricky to insert. Make sure everything is properly aligned before you apply pressure, otherwise you might break the connector. Plug the opposite end of each cable (or series of daisy-chained cables) into a headstage, or a headstage Y-adapter, if you're using two headstages on one port.

    .. image:: ../_static/images/usermanual/quickstart/spi_cable.jpg
      :width: 70%
      :align: center

#. **Connecting peripheral devices**

    *Required components: I/O Board, HDMI cable*

    External devices that generate digital or analog signals can interface with Open Ephys system through an I/O board. We use HDMI cables to connect to the I/O board, as these are cheap and have exactly the right number of shielded wires inside of them. Please note that these ports are not standard HDMI points; they will not work with any HDMI-compatible devices.

|

    The HDMI connections on the acquisition board are as follows:

|

    .. image:: ../_static/images/usermanual/quickstart/in_out_label.png


#. **Operation**

    This section assumes you have compatible acquisition software installed (likely the Open Ephys GUI or Bonsai). Check out :ref:`this page <acquisitionsoftware>` for more info.

    These are some things to keep in mind:

    *Using a laptop*

    If you're using the acquisition board with a laptop that's running off battery power, you will have a "floating" ground. This will cause your signals to look extremely noisy. To fix the issue, connect the ground of the acquisition board to whatever ground you're using for your experimental setup (perhaps a wall socket or a Faraday cage). You can either do this via the BNC connector (alligator clips work well for this), or by attaching a wire to one of the two dedicated screw terminals on the side of the board. The screw terminals are preferred because the BNC may be needed for another purpose. 
    
    .. caution:: If you use the BNC for grounding, be extra careful to attach your ground wire to the exterior shell, not the center pin. Connecting the center pin of the BNC to ground will short your board and may fry the FPGA.

    *Analog inputs*

    There is a small DC offset (~0.4 V) on the ADCs when they're in ±5V range. This offset is taken into account by the Open Ephys GUI, but since the offset can be slightly different for each channel, the traces may not be exactly centered around zero. Be sure to measure the "zero" value for each channel if you're doing any analysis that depends on absolute DC values and applying a high-pass filter is not possible.

    .. note:: If any of the ADC channels are not connected (i.e., the signal pin is floating), signals from adjacent channels will bleed through. This is expected behavior.

    *LEDs*

    The LEDs on the acquisition board will flash during normal operation. Fast flashing of the left-most LED (analog output) is expected. The digital input LED should turn green when one of the digital input channels is high, which is useful for checking whether or not your synchronization is working.

    It is possible that the LEDs can create noise in your recordings for some grounding configurations. You may also want to disable them if you're performing behavioral experiments in the dark. The LEDs can be turned off by clicking the "LED" button in the `Rhythm FPGA <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Rhythm-FPGA.html>`_ plugin in the Open Ephys GUI.

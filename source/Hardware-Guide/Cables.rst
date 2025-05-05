.. _cables:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Cables
***********************************

To start using the Acquisition Board, you'll need the following cables:

:ref:`1_powercable`

:ref:`2headstage`

:ref:`3usb`

:ref:`iohdmi`

.. image:: ../_static/images/usermanual/cables/all_cables.png
  :width: 70%
  :align: center

.. _1_powercable:

1. Power cable
###################################
If you buy the Acquisition Board from the `Open Ephys store <https://open-ephys.org/store>`_ it ships with a wall adapter (to 5V) power supply that you can safely use with the board. Though the most recent versions have over-voltage protection, this isn't limitless so be careful to use the correct adapter when powering the board.

.. _2headstage:

2. Headstage to Acquisition Board cable
######################################################################
For recordings in freely behaving mice, it is important to minimize the weight and torque applied by the cables. This is especially important for experiments that require natural behavior and becomes a real issue for channel counts over 32 where even light wire tethers become bulky.

The standardized interface cable for Intan RHD chips we use is ideal for this application. Thanks to the `digital LVDS signal <https://en.wikipedia.org/wiki/Low-voltage_differential_signaling>`__, only 12 conductors are needed for transmitting up to 64 channels of neural data. Cables that conform to this standard can be purchased from the Intan website in 3- or 6-foot lengths. The cables for the acquisition board must conform to the SPI standard `specified by Intan <http://www.intantech.com/files/Intan_RHD2000_SPI_cable.pdf>`_

The current standard cable contains 2 MISO (headstage->computer) data lines, so it's possible to connect 2 headstages to one input on the acquisition board via one cable by using a `Y-adapter <https://intantech.com/RHD_SPI_cables.html?tabSelect=RHDdual&yPos=0>`_. For connectors we're using 12-pin Omnetics PZN-12 polarized nano connectors.

You can also make fine wire tethers :ref:`yourself <custom_cables>`.

Intan cables
***********************************

`Details are available on the Intan website <https://intantech.com/RHD_SPI_cables.html?tabSelect=RHDSPIcables&yPos=100>`_. Intan cables are available as standard or ultra-thin, and the choice will depend on how much cable mass (and subsequent weight and torque) will influence your experiments, as well as how long you need your cable to be.

Dual-headstage adapter
***********************************

The `dual-headstage adapter <https://intantech.com/RHD_SPI_cables.html?tabSelect=RHDdual&yPos=100>`_ takes advantage of the 2 headstage-computer data lines in the SPI cable and exposes each line to a separate Omnetics connector, so that you can run two headstages off one cable. If you plan to use this adapter with daisy-chained cables resulting in a cable longer than 1.8 meters, be sure to `read the documentation <https://intantech.com/files/Intan_RHD2000_dual_headstage_adapter.pdf>`_ to make the necessary adjustments to the resistors on the adapter, or you risk corrupting your data. You can also make dual headstage adapters :ref:`yourself <custom_cables>`.

.. _3usb:

3. USB cable
####################################################
To connect the Acquisition Board to a computer, use a USB-3 cable with a Micro-B USB3 connector on the Acquisition Board end.

.. _iohdmi:

4. Input/Output Board to Acquisition Board cable
####################################################
This is an HDMI Type A to HDMI Type A cable. Note that the input is not an actual HDMI input, so don't connect real HDMI devices to the Acquisition Board ports.

If you just need one or two channels in a hurry, you can :ref:`make a quick adapter cable<customBNC>` with pretty little effort.

There are also a variety of simple HDMI breakout boards available from various vendors - these work equivalently as I/O boards. See for instance `here <https://elabbay.myshopify.com/collections/breadboard/products/elabguy-hdmi-af-bo-v1a-hdmi-type-a-female-socket-breakout-board>`_.
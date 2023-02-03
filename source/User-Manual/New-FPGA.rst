.. _newfpga:

New Open Ephys FPGA module
=====================================================
*Last updated: 3rd Feb 2023*

Devices shipped from Dec 2022 onwards use a brand-new FPGA module designed by Open Ephys.

These boards need a different driver and Open Ephys GUI plugin to work.

Before attempting to use one, please follow the installation instructions below. 

.. important:: You will need to install and use:

    * A different driver, **FTD3XXDriver**
    * A different plugin, **OE FPGA Acquisition Board** for GUI v0.6 (currently Windows only)
    * The latest gateware, **v0.4**

.. _newfpga_instructions:

Instructions (currently Windows only)
--------------------------------------

.. _newfpga_driver:

1. Install the driver
**********************

The new FPGA uses different drivers that need to be installed before plugging the device to your computer.
   
   #. Download the drivers `here <https://www.ftdichip.com/Drivers/D3XX/FTD3XXDriver_WHQLCertified_v1.3.0.4_Installer.exe.zip>`_.
   #. Unzip the folder
   #. Run ``FTD3XXDriver_WHQLCertified_v1.3.0.4_Installer.exe``

.. _newfpga_guiversion:

2. Make sure your Open Ephys GUI version is up to date
*******************************************************

The new plugin works in version v0.6 of the GUI and above.
   
   #. Download the latest version of the Open Ephys GUI `here <https://open-ephys.org/gui>`_.
   #. Double-click the downloaded executable to launch the installer.
   #. Follow the installer instructions.

.. _newfpga_plugin:

3. Install the plugin (currently Windows only)
**********************************************

You now need to install the new plugin in the Open Ephys GUI v0.6 or above.

   #. Within the Open Ephys GUI, select ``Plugin Installer`` from the ``File`` menu.
   #. Find the ``OE FPGA Acquisition Board`` plugin and click ``Install``. *Always use the latest version of the plugin*

.. _newfpga_gateware:

4. Make sure you have the latest gateware
*****************************************

We have released several improvements since the first batch of boards went out, so depending on when you got your board, you might not have the latest gateware.

Follow the instructions on the :ref:`gwupdate` page to check your gateware version and update it.

5. Test and use your board!
*****************************

You can now use this plugin to acquire data from your acquisition board. Usage instructions for the board can be found in this User Manual and for the plugin, in the `Rhythm Plugins page <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Rhythm-Plugins.html>`_ of the OE GUI documentation.

Avoid confusing the new ``OE FPGA Acquisition Board plugin`` with the one called ``Acquisition Board`` which was used for previous versions of the acquisition board that did not have the Open Ephys FPGA. We are working on integrating them in the same plugin but for the moment, these are two separate plugins. Your new board will not work with the old plugin and vice versa.

As with any new device, test your acquisition board to make sure it is working as expected by performing checks on a short recording before using it for research. We test them before they get to you but might not have covered all the use cases and your particular hardware. 

.. _newfpga_help:

If you need help or are experiencing issues
--------------------------------------------
Please reach out to *support@oeps.tech* with these details:

* tell us you have an acquisition board with the new FPGA module
* copy & paste the complete contents of the console log (from the console window that opens at the same time as the GUI)
* include a screenshot or photo of the issue


.. _newfpga_development:

Under development
-------------------
We will continue to work on getting the full integration of the board with the new FPGA module that the previous boards had. These functionalities are underway:

* New OE FPGA Acquisition board plugin for Mac and Linux. If you need to use these OS, let us know and we will compile it for you.
* Unified OE GUI plugin for all acquisition boards regardless of the FPGA module they have

.. _newfpga_differences:

Differences with previous boards
-----------------------------------

* **This board only has one power port. Always use the 5V power supply provided.**

Since this new FPGA module was developed by us, it has the voltage protection circuitry we require for use with the acquisition board.

* **The power light inside the board is now red.**

The LED that indicates that the FPGA module is powered used to be green on the FPGA module we used previously, but on our new one it is red.

The green LEDs on the left indicate different statuses so they can be used to troubleshoot.

* **The device name is now Open Ephys FT600 USB board.**

The FPGA module is no longer a development board created by Opal Kelly. Instead, we have designed it at Open Ephys based on a Lattice ECP5 FPGA. It uses an FTDI FT600 USB chip, which explains the new name.

You should find it listed in ``Settings > Devices`` under “Other devices” with the name ``Open Ephys FT600 USB board``.

In the Device Manager, it is sometimes listed under ``Other devices`` as ``Open Ephys FT600 USB board`` and other times only the USB controller is shown, as ``FTDI FT600 USB 3.0 Bridge Device``. If you see a warning icon, you have to :ref:`install the driver<newfpga_driver>`.

* **It uses a different OE GUI plugin and Bonsai package.**

Until software integration is complete, the acquisition board with the new FPGA module uses a different plugin in the OE GUI and a different package in Bonsai than the previous boards.

   The OE GUI plugin is: ``OE FPGA Acquisition Board``

   The Bonsai package is: ``Bonsai.OpenEphys``

* **Plugin initialization takes slightly longer.**

It takes a little more time  than previously to initialize the plugin (every time you add the OE FPGA Acquisition Board plugin to the signal chain). This is something we are aware of and are working on improving. It also happens at runtime when using the new Bonsai node.

Additionally, this new FPGA module performs a self-initialization on power up (for approximately 20 sec after it is first connected to the power supply). If you try to use the OE FPGA Acquisition Board plugin during this time, you will see the following message in the console: 

And the plugin will wait until it is completed to continue loading. The GUI might appear non responsive during this time:

This will not appear if the node is created after the board has performed this self-initialization.

* **The bitfile is stored permanently on the board. Make sure you update to the latest gateware version.**

In this new FPGA module, the bitfile is not uploaded by the OE GUI each time the board is recognized, but resides permanently on the board. This makes it easier  to use it across different software like Bonsai as it avoids bitfile path issues.

However, this means that if there are any updates to the gateware you have to upload the bitfile manually. Gatware updates are not common after an initial period during which any bugs are resolved. For reference, the bitfile for the old board has changed less than 10 times in 7 years. You can update the gateware on your FPGA module by following the instructions on the :ref:`gwupdate` page.

.. _newfpga_contribute:

Contribute
------------
We count on user feedback to improve our devices, as we test them before they get to you but might not have covered all the use cases and your particular hardware. Always test new devices by performing checks on a short recording before using them for research.

If you find any problems, please let us know and we will address them as fast as we can. We would appreciate it if you can post a GitHub Issue to the plugin repository `here <https://github.com/open-ephys-plugins/rhythm-oni-plugin/issues>`_.

While acquisition board usage is the same, we will be slowly updating the documentation to reflect these changes. You are welcome to contribute to our documentation `here <https://github.com/open-ephys/acq-board-docs>`_.

.. _newfpga_why:

Why and how did we make this happen?
-------------------------------------
Our acquisition board relies on an FPGA (Field-Programmable Gate Array) to control data acquisition and timestamp the incoming data (see the details on the :ref:`howitworks` page). The Opal Kelly FPGA module we used in previous acquisition boards was end-of-lifed all of a sudden at the end of 2021 and it immediately ran out of stock.

The Open Ephys team, led by Aarón Cuevas López developed a completely new module with the scarce components available despite the ongoing silicon shortage. This module uses the same footprint as the previous one, so it can be replaced directly on the existing acquisition boards, although it uses a different FPGA, a Lattice EPC5, and its `design is open source <https://github.com/open-ephys/ECP5U85-BSE-USB>`_. Additionally, communication with the computer follows our new ONI standard for common interfaces in neuro tools (the same standard that powers our next-gen system, `ONIX <http://open-ephys.github.io/onix-docs/>`_).

In under a year, this new design went into production and we started to ship to users that had been waiting eagerly for new boards and repaired boards. Software integration quickly followed, to provide users with the same functionality they know and have come to rely on for their research over the past decade.

.. _newfpga_licenses:

External Licenses
---------------------------
The Open Ephys FPGA board makes use of `LiteDRAM <https://github.com/enjoy-digital/litedram>`_ as a memory controller.

   *Unless otherwise noted, LiteDRAM is Copyright 2012-2022 / EnjoyDigital*
   *Initial development is based on MiSoC's LASMICON / Copyright 2007-2016 / M-Labs*

   *Redistribution and use in source and binary forms, with or without modification,*
   *are permitted provided that the following conditions are met:*

   *1. Redistributions of source code must retain the above copyright notice, this*
   *list of conditions and the following disclaimer.*

   *2. Redistributions in binary form must reproduce the above copyright notice,*
   *this list of conditions and the following disclaimer in the documentation*
   *and/or other materials provided with the distribution.*

   *THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.*
   *Other authors retain ownership of their contributions. If a submission can reasonably be considered independently copyrightable, it's yours and we encourage you to claim it with appropriate copyright notices. This submission then falls under the "otherwise noted" category. All submissions are strongly encouraged to use the two-clause BSD license reproduced above.*

.. :ref:`newfpga_licenses`
.. ``UpdateFPGA_v0_4.bat``

.. .. note:: The programmer might appear frozen at some percentages, but it is working. 
..     In the rare case that something went wrong and it got stuck for more than **5 minutes**
..     it is safe to try again, just by unplugging the board from power and usb, 
..     plugging it again and executing the updater.

.. .. image:: /_static/images/usermanual/gateware/GUI-message.png
..     :width: 80%
..     :align: center
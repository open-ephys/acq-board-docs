.. _troubleshooting:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Troubleshooting Guide
***********************************

Here is a guide to help you troubleshoot common error scenarios that can occur when using the Acquisition Board. It is focused on generations of the Open Ephys Acquisition Board with the OE FPGA module and Open Ephys GUI usage in Windows.

If issues persist after following this guide, or the scenario you encountered is not in this guide, please reach out as detailed under :ref:`help`.

General recommendations
###################################

- Know what generation of the Acquisition Board you have and which FPGA module it uses. See the :ref:`Differences Between Generations section <genids>` to identify this.
- Keep the software and plugins/packages that run the Acquisition Board updated to the latest version. Check the software documentation for information on how to achieve this.
- Keep the gateware of your Acquisition Board updated to the latest version. The :ref:`gwupdate` section explains how to do this for the Open Ephys FPGA module in Gen2 and above. Previous generations of the acquisition board use a gateware bitfile distributed with the Open Ephys GUI which is no longer revised.
- Keep an eye out for warnings and errors in the software console during operation.
- :ref:`Configure the USB settings <usb-config>` to avoid suspension due to power management, which interferes with USB communication.

.. _initial-troubleshooting:

Initial troubleshooting steps
###################################

.. _isitconnected:

1. Check the hardware connections to power and USB
******************************************************************

- Always plug the board into power using the original 5V, 2A power adapter provided. 
- Use a USB 3.0-compatible port on your computer using the high-speed USB cable provided. USB 3.0-compatible port are usually indicated by a blue color and are often at the back of PCs. Ensure you establish a reliable USB connection by connecting directly to the port instead of through a hub or extension. USB cables longer than 2 meters are not recommended.

*You should see a red light turn on continuously inside the board beside the USB connection.*

.. _isitrecognized:

2. Check that the board is recognized properly by the Operating System
*******************************************************************************
.. what about OS other than Win?

After making sure to follow step :ref:`isitconnected`, the Acquisition Board should be recognized by the Operating System.

..  tab-set::
    :sync-group: os

    ..  tab-item:: Windows

        **Check that the board is recognized by the OS, connected to USB3.0 and drivers are installed:**

        Go to :code:`Start Menu > Settings > Devices > Bluetooth & other devices` or to the Device Manager, and check that the board is listed as *Connected to USB3.0*, with no additional warnings.

        .. image:: /_static/images/usermanual/troubleshoot/board_recognized.png
            :width: 60%
            :align: center

        - If the board is not listed, troubleshoot the USB connection by checking different USB ports, USB cables and computers to rule out a hardware issue.
        - If the board is listed as connected to USB 2.0, then connect the board to a 3.0 USB port.
        - If there is a warning about drivers issues, :ref:`re-install the drivers <drivers>`.

    ..  tab-item:: Linux
        
        **Check that the board is recognized by the OS:**

        1. Open a terminal. Root permissions are not required.
        2. Enter :code:`lsusb -d 0403:601e`. The output should list the board, including the Bus and Device numbers required to talk to the board. These numbers change every time the board is re-connected:

        .. code-block:: console

            $ lsusb -d 0403:601e
            Bus 002 Device 004: ID 0403:601e Future Technology Devices International, Ltd Open Ephys FT600 USB board

        - If the board is not listed, troubleshoot the USB connection by checking different USB ports, USB cables and computers to rule out a hardware issue.

        **Check that the board is connected to USB3.0:**

        3. Enter :code:`lsusb -v -d 0403:601e | grep "bcdUSB"`. The output should be 3.x for USB3. Ignore any other messages that might appear when running this command:

        .. code-block:: console

            $ lsusb -v -d 0403:601e | grep "bcdUSB"
            bcdUSB              3.10 

        - If the output says 2.x, then connect the board to a 3.0 USB port.

        **Check that the board permissions are properly configured:**

        4. Enter :code:`ls -l /dev/bus/usb/XXX/YYY` where XXX is the Bus number and YYY the Device number found in step 2 above. The output should start with :code:`crw-rw-rw-`.

        .. code-block:: console

            $ ls -l /dev/bus/usb/002/004
            crw-rw-rw- 1 root root 189, 132 Jan 23 22:00 /dev/bus/usb/002/004    

        - If the output is something other than :code:`crw-rw-rw-`, then :ref:`re-configure the board permissions <drivers>`.

.. _isitfound:

3. Check that the board is detected by the software
******************************************************************

If you encounter the error message "No device found" in the Open Ephys GUI:

.. image:: /_static/images/usermanual/troubleshoot/board_not_found.png
    :width: 40%
    :align: center

Make sure to follow step :ref:`isitconnected` and step :ref:`isitrecognized`. Then,

1. :ref:`Re-install the latest version of the drivers/re-set the board permissions <drivers>`.
2. Update the Acquisition Board plugin to the latest version. Start from an empty signal chain (go to :code:`Edit > Clear signal chain` or press :code:`Ctrl + backspace`). Then, go to :code:`File > Plugin Installer` or press :code:`Ctrl + P` to access the `Plugin Installer <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/index.html#plugin-installer>`_, find the Acquisition Board plugin and click "Upgrade".
3. :ref:`Update the gateware <drivers>`.

.. _usb-config:

USB configuration
###################################

The PC's power management both in laptops and desktops can interfere with USB communication. This can be experienced as a sudden interruption during an otherwise stable period acquisition that can be traced back to USB communication errors and not a hardware disconnection.

Always ensure that the USB settings are configured to avoid suspension.

On Windows desktops, go to :code:`Control Panel > Hardware and Sound > Power Options > Edit Plan Settings`, and into the Advanced Power Settings. 

.. image:: /_static/images/usermanual/troubleshoot/power-settings.png
    :width: 80%
    :align: center

Change the settings for the power plan that you are using to ensure that the USB selective suspend setting is Disabled.

.. image:: /_static/images/usermanual/troubleshoot/power-advanced-settings.png
    :width: 40%
    :align: center

On Windows laptops, a similar option to disable the USB battery saver is available under :code:`Settings > Bluetooth & Devices > USB`

.. image:: /_static/images/usermanual/troubleshoot/usb-settings-laptop.png
    :width: 70%
    :align: center

.. _help:

How to ask for help
###################################

1. Make sure that you have read through this guide.
2. Check that the software application, the plugin/package, the drivers and the acquisition board gateware are all updated to the latest version.
3. Check the software console or activity log for any errors or warnings.
4. Write to our `support channel <https://open-ephys.org/contact>`_ with the following information:

- Details of your hardware setup including you Acquisition Board generation and all hardware connections.
- A photo, screenshot or screen capture showing the issue.
- A description of what happened as the issue occurred.
- For software issues, please send the complete contents of the console log. In the Open Ephys GUI, go to :code:`View > Console` or press :code:`Shift + C` to toggle the console window into view and click "Copy All" on the top right. If the GUI crashed and the console window shut down, then please send the corresponding activity `log file  <https://open-ephys.github.io/gui-docs/User-Manual/Exploring-the-user-interface.html#log-files>`_. 

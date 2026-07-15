.. _drivers:

Driver installation
=====================================================

Drivers are distributed with the Open Ephys GUI, so you will usually be able to complete the driver installation during the `Open Ephys GUI installation <https://open-ephys.github.io/gui-docs/User-Manual/Installing-the-GUI.html>`_. If you run into issues or need to install them independently, please follow the instructions below. 

.. note:: Different Acquisition Board generations use different drivers. See :ref:`this section <genids>` to identify what generation board you have.

Make sure you have the drivers installed correctly before using the Acquisition Board.

Driver installation for Generations 2 and above
-----------------------------------------------------------------------------------

Acquisition Boards with an OE FPGA module (Open Ephys FT600 USB board) require the **FTD3XXDriver**.

On Windows 
********************
   
#. Download the `Windows driver <https://github.com/open-ephys-plugins/ftdi-drivers/raw/refs/heads/main/installers/FTDI_DriverInstaller_1.4.0.1_x64.exe>`__.
#. Run ``FTDI_DriverInstaller_1.4.0.1_x64.exe``

On MacOS 
********************
   
#. Download the `MacOS driver <https://github.com/open-ephys-plugins/acquisition-board/blob/main/Resources/Drivers/libftd3xx.dylib>`__.
#. Copy the file ``libftd3xx.dylib`` to ``/usr/local/lib`` (you can use ``sudo cp libftd3xx.dylib /usr/local/lib``)

Some security features on mac might prevent the driver from loading.

.. image:: /_static/images/usermanual/newfpga/Mac-driver-security-popup.png
    :width: 30%
    :align: center

The steps to solve this are:

#. Go to system settings
#. Go to the Security and Privacy section
#. Unlock the page by clicking on the lower-left padlock icon. It will ask for your password
#. Near the bottom of the page, the library error will appear, click on allow
#. Run the updater again, if a window appears, it will have an ``open`` option now

On Linux
********************

Linux does not require a driver, but the board permissions need to be configured. These are configured during the Open Ephys GUI installation, but if you need to configure board permissions independently, you can manually copy the rules file from the `zip version of the installer <https://open-ephys.github.io/gui-docs/User-Manual/Installing-the-GUI.html#via-zip-file-all-distros>`_ or your own build. 

#. Open a terminal and set your working directory to the main folder of the GUI source code.

#. Enter :code:`sudo cp Resources/Scripts/40-open-ephys.rules /etc/udev/rules.d`. The console might then ask for your password.

#. Enter :code:`service udev restart` on Ubuntu/Debian or :code:`sudo udevadm control --reload-rules` on Fedora/CentOS/Gentoo to allow the GUI to communicate with the Open Ephys acquisition board.

The changes will take effect the next time the Acquisition Board is connected to USB.

Driver installation for Generations 0 and 1
-----------------------------------------------------------------------------------

Acquisition Boards with an Opal Kelly FPGA module require the **FrontPanelUSB Driver**.

On Windows 
********************
   
#. Download the `Windows driver <https://github.com/open-ephys/plugin-GUI/blob/main/Resources/DLLs/FrontPanelUSB-DriverOnly-4.5.5.exe>`_.
#. Unzip the folder
#. Run ``FrontPanelUSB-DriverOnly-4.5.5.exe``

.. On MacOS 
.. ********************

.. Confirm drivers are properly installed
.. -------------------------------------------------------


.. Troubleshooting drivers (driver version check)
.. -------------------------------------------------------
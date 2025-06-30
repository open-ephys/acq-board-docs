.. _drivers:

Driver installation
=====================================================

Here are the instructions to install the drivers to use the Acquisition Board.

.. note:: Different Acquisition Board generations use different drivers. See :ref:`this section <genids>` to identify what generation board you have.

Make sure you have the drivers installed correctly before using the Acquisition Board.

Drivers are distributed with the Open Ephys GUI, so you will usually be able to complete the driver installation during the Open Ephys GUI installation. If you need to install them independently, please follow the instructions below. 

Driver installation for Generations 2 and above
-----------------------------------------------------------------------------------

Acquisition Boards with an OE FPGA module (Open Ephys FT600 USB board) require the **FTD3XXDriver**.

On Windows 
********************
   
#. Download the `Windows driver <https://github.com/open-ephys/plugin-GUI/raw/refs/heads/main/Resources/DLLs/FTD3XXDriver_WHQLCertified_1.3.0.10_Installer.exe>`__.
#. Run ``FTD3XXDriver_WHQLCertified_1.3.0.10_Installer.exe``

On MacOS 
********************
   
#. Download the `MacOS driver <https://github.com/open-ephys-plugins/rhythm-oni-plugin/raw/refs/heads/main/Resources/Drivers/libftd3xx.dylib>`__.
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
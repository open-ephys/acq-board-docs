.. _gwupdate:

Gateware Updates
=========================================

Here are the files and instructions to update the Open Ephys FPGA module inside
the Acquisition Board.

.. note:: This is only for boards that use the new Open Ephys FPGA module. We always ship the boards 
    with the latest version of the gateware and we don’t make changes to the gateware often, so you 
    will typically not need to update it. Generations 0 and 1 of the Acquisition Board, which use the Opal Kelly FPGA,
    do not require this.

.. _gwupdate_latest:

Latest version
-------------------------

The latest gateware version for Acquisition Board 2nd and 3rd Generation. Select the updater for your operating system.

See :ref:`this section <genids>` to identify what generation board you have.

.. list-table::
   :widths: 15 25 60
   :header-rows: 1

   * - Operating System
     - Version
     - Release Date
   * - Windows
     - :download:`version 2.0.0 </_static/files/OpenEphysFPGA-gw2.0-win64.zip>`
     - 2026.07.16
   * - Linux
     - :download:`version 2.0.0 </_static/files/OpenEphysFPGA-gw2.0-linux.tar.gz>`
     - 2026.07.16
   * - MacOS
     - :download:`version 2.0.0 </_static/files/OpenEphysFPGA-gw2.0-macOS.tar.gz>`
     - 2026.07.16

.. note:: To run this updater on Windows, driver version 1.4.0.1 or greater is required.
    Instructions are available on the :ref:`driver installation page<drivers>`.

.. warning:: Version 2.0.0 and higher of the firmware require a version 2.0 or higher
    of the `acquisition board plugin <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Acquisition-Board.html>`__
    for the `Open Ephys GUI <https://open-ephys.github.io/gui-docs/index.html>`__.

.. _gwupdate_instructions:

Determining current gateware version
---------------------------------------

In the Open Ephys GUI 
***************************

After dragging the ``OE FPGA Acquisition Board`` plugin to the signal chain, a message in the console
will appear, with the current running gateware.

.. image:: /_static/images/usermanual/gateware/GUI-message.png
    :width: 80%
    :align: center

In Bonsai
*********************************

After creating the ``Source/OpenEphys/AcquisitionBoard`` node, the properties at the
right of the window will contain a ``GatewareVersion`` field.

.. image:: /_static/images/usermanual/gateware/Bonsai-version.png
    :width: 30%
    :align: center

If the version does not appear or appears as ``N/A`` when creating the node, it will be properly
updated after acquisition starts.

Updating gateware
--------------------------------------------------------------------------------

.. warning:: Do not attempt to update the board gateware while the GUI or any other software using
    the board is in use. Do not open any software that uses the board while an update is in process.

#. Make sure that the correct and latest :doc:`device drivers are installed </User-Manual/Driver-installation>`

#. Connect the acquisition board to the computer via USB 3.0 and connect it to power using the power supply provided.

#. Confirm that the device is recognized by the operating system. If not, follow the :ref:`Troubleshooting Guide <isitrecognized>`. 

#. Download the :ref:`gwupdate_latest` of the gateware for your operating system and extract the contents of the file.

#. Run the updater:

   * On Windows: Double click on the file ``UpdateFPGA.bat``
   * On Linux or Mac: Execute the file ``UpdateFPGA.sh``

#. Wait a couple of minutes for the process to finish.

.. note:: The programmer might appear frozen at some percentages, but it is working. 
    In the rare case that something went wrong and it got stuck for more than **5 minutes**
    it is safe to try again, just by unplugging the board from power and usb, 
    plugging it again and executing the updater.

Notes on Mac
*************************

Some security features on mac might prevent the updater from running. A message
indicating that ``libftd3xx.dylib`` is not signed might appear. The steps to solve
this are:

#. Go to system settings
#. Go to the Security and Privacy section
#. Unlock the page by clicking on the lower-left padlock icon. It will ask for your password
#. Near the bottom of the page, the library error will appear, click on allow
#. Run the updater again, if a window appears, it will have an ``open`` option now

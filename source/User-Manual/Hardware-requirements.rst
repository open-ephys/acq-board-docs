.. _hardwarerequirements:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Hardware Requirements
***********************************

.. figure:: /_static/images/usermanual/quickstart/complete_system_labeled.png
   :width: 70%
   :align: center

   An example acquisition system using the Acquisition Board, a low-profile headstage and a commutator. Remember to plug in the power supply and to ground your system. Use I/O Boards for digital and analog inputs and outputs.

.. _acsystemparts:

Minimal Components for a Complete Acquisition System 
#####################################################

A complete data acquisition system consists of the following hardware:

* An Acquisition Board, which you can either order from the `Open Ephys store <https://open-ephys.org/store>`_ or build yourself by following the :ref:`buildinstructions` section of this documentation.

* USB 3.0 cable

* 5V power supply

* At least one :ref:`headstage <headstages>` with an Intan RHD-series chip, which you can order from the Open Ephys store or the Intan website, or build yourself. Each headstage can handle 16 to 128 channels of neural input.

* One :ref:`cable <cables>` to connect each headstage to the acquistion board, which you can order from the Open Ephys store (as part of the starter kit) or the Intan website, or build yourself.

* (Optional) One or more :ref:`I/O boards <peripheraldevices>` for auxiliary (non-neural) signals. Each I/O board requires one HDMI cable to connect to the acquisition board.

* A :ref:`computer <computerhardware>` to run the software and interface with the rest of the system. The recommended configuration depends on the number of channels you plan to acquire simultaneously.

If you already have these components, follow the :ref:`quickstartguide` to learn how to start collecting data right away. Otherwise, we recommend reading through the sub-pages of this documentation to help you decide which components to buy.

.. _computerhardwere:

Acquisition Computer
======================

A computer with the following specifications is recommended for experiments that use the acquisition board:

*   **Operating system**: Depends on which software you want to use:
    
    *   Open Ephys GUI: compatible with macOS, Windows, and Linux (all distros)
    
    *   Bonsai: compatible with Windows
        
        ..  attention::
            The Bonsai.Ephys Bonsai package does not support all generations of the acquisition board. Visit the :doc:`Generations-differences` page to figure out if your acquisition board is compatible with Bonsai.

* **Processor** - A 4-core, 3.0+ GHz processor is fine for 32-channel recordings, but you'll want more cores and more speed as you scale up. Having a faster processor will allow you to build more complex signal chains without worrying about CPU overload. The GUI uses multithreading for data acquisition and recording, so having more cores is also helpful.

* **Memory** - at least 1 GB of memory per 32 channels.

* **Data storage** - a solid state drive is *strongly* recommended, and required for any recordings involving more than 128 channels.

* **Graphics card** - a good graphics card is not critical for data acquisition. However, consider upgrading your graphics card to speed up offline analysis steps (such as spike sorting).

* **Ports** - At least one USB 3.0 port
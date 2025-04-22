.. _hardwarerequirements:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Hardware Requirements
***********************************

.. _computerhardwere:

Acquisition Computer
###################################

A computer with the following specifications is recommended for experiments that use the acquisition board:

* **Operating system** - the acquisition board works equally well on macOS, Windows, and Linux (all distros).

* **Processor** - A 4-core, 3.0+ GHz processor is fine for 32-channel recordings, but you'll want more cores and more speed as you scale up. Having a faster processor will allow you to build more complex signal chains without worrying about CPU overload. The GUI uses multithreading for data acquisition and recording, so having more cores is also helpful.

* **Memory** - at least 1 GB of memory per 32 channels.

* **Data storage** - a solid state drive is *strongly* recommended, and required for any recordings involving more than 128 channels.

* **Graphics card** - a good graphics card is not critical for data acquisition. However, consider upgrading your graphics card to speed up offline analysis steps (such as spike sorting).

* **Connections** - At least one USB 3.0 port

.. _acsystemparts:

Acquisition System Components
###################################

A complete data acquisition system consists of the following hardware:

* An Acquisition Board, which you can either order from the `Open Ephys store <https://open-ephys.org/store>`_ or build yourself by following the :ref:`buildinstructions` section of this documentation.

* USB 3.0 cable

* 5V power supply

* At least one :ref:`headstage <headstages>` with an Intan RHD-series chip, which you can order from the Open Ephys store or the Intan website, or build yourself. Each headstage can handle 16 to 128 channels of neural input.

* One :ref:`cable <cables>` to connect each headstage to the acquistion board, which you can order from the Open Ephys store (as part of the starter kit) or the Intan website, or build yourself.

* (Optional) One or more :ref:`I/O boards <peripheraldevices>` for auxiliary (non-neural) signals. Each I/O board requires one HDMI cable to connect to the acquisition board.

* A :ref:`computer <computerhardware>` to run the software and interface with the rest of the system. The recommended configuration depends on the number of channels you plan to acquire simultaneously.

If you already have these components, follow the :ref:`quickstartguide` to learn how to start collecting data right away. Otherwise, we recommend reading through the sub-pages of this documentation to help you decide which components to buy.

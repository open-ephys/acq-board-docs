.. _hardwareguide:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Hardware Guide
***********************************

You can follow the :ref:`quickstartguide` to learn how to start collecting data right away.
However, we recommend reading this section carefully if you're going to use our hardware, and especially if you're going to build it. When something goes wrong, or if your data look suspicious, knowing the basics of how the hardware works will make it easier to troubleshoot. And the more people who have a thorough understanding of the Open Ephys ecosystem, the easier it will be to support new users.

We're going to assume a basic understanding of electronic circuits. If you don't have any hands-on experience working with electronics, check out our free course materials on extracellular electrophysiology acquisition `here <https://ahleighton.github.io/OE-ephys-course/>`_, which also covers the basic electronics you will need. It would also be helpful to read through the documentation available on the `Intan website <https://intantech.com/products_RHD2000.html>`_ to learn more about the RHD2000 chip.

.. note:: From December 2022 the acquisition board features a new FPGA designed by Open Ephys.
   Among other differences, the new board stores the bitfile for its gateware internally.
   It is recommended to check the :ref:`gwupdate` page to keep your board updated.

.. toctree::
    :hidden:
    :maxdepth: 1
    :titlesonly:

    Electrodes
    Cables
    Headstages
    How-it-works
    Status-LEDs
    Peripheral-devices



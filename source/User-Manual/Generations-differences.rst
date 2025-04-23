.. _gendiffs:

Differences Between Generations
=========================================

Over the years, the Acquisition Board original design has been had modifications and improvements.

Different combinations of the Acquisition Board main board and the FPGA module make up different Acquisition Board generations. 

Even though newer generations are backwards compatible and all generations generally work in the same way, there are some differences worth keeping in mind.


Hardware Differences
-------------------------

These details will help you identify what board generation you have.

.. csv-table:: 
   :file: /_static/files/gen-hardware-diff.csv
   :widths: 16, 14, 14, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   
.. _genids:

Identifying Acquisition Board Generations
***************************************************************

.. figure:: /_static/images/usermanual/generations/gen1_back.png
   :scale: 80%
   :align: center

   Gen 1 Acquisition Boards have two power supply inputs, one on the Opal Kelly XEM6310-LX45 FPGA module and one on the main board.

.. figure:: /_static/images/usermanual/generations/gen2_back.png
   :scale: 80%
   :align: center

   Gen 2 Acquisition Boards have a single power supply input on the Open Ephys FT600 USB board FPGA module. 

.. figure:: /_static/images/usermanual/generations/gen2_back.png
   :scale: 80%
   :align: center

   Gen 3 Acquisition Boards have a single power supply input on the Open Ephys FT600 USB board FPGA module and a Harp input. The case has the 3d logo on the top.

Drivers, Gateware and Software Compatibility
------------------------------------------------------

Different board generations use different drivers, have different software compatibility and use different gateware.

.. csv-table:: 
   :file: /_static/files/gen-driver-gateware-software-diff.csv
   :widths: 16, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   

Functionality Differences
------------------------------------------------------

Board generations have functionality differences.

.. csv-table:: 
   :file: /_static/files/gen-functionality-diff.csv
   :widths: 16, 14, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   

.. could add some styling to these tables using https://stackoverflow.com/questions/79112627/in-sphinx-how-do-i-style-a-csv-table
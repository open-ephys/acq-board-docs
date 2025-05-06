.. _gendiffs:

Differences Between Generations
=========================================

The Acquisition Board design has evolved over the years to add features and improvements.

Different combinations of the Acquisition Board main board and the FPGA module make up different Acquisition Board generations. 

Although newer generations are backwards compatible and all generations generally work in the same
way, there are some important distinctions to consider. This page contains about information about
these distinctions.

.. _genids:

Identify Your Acquisition Board
***************************************************************

.. list-table::
   :widths: 40 60
   :align: center

   * - .. figure:: /_static/images/usermanual/generations/acq_board_back_gen3.png
          :align: center
     - **Gen 3** Acquisition Boards have a single power supply input on the Open Ephys FT600 USB board FPGA module and a Harp Clk output. The case has the 3d logo on the top.
   * - .. figure:: /_static/images/usermanual/generations/acq_board_back_gen2.png
          :align: center
     - **Gen 2** Acquisition Boards have a single power supply input on the Open Ephys FT600 USB board FPGA module. 
   * - .. figure:: /_static/images/usermanual/generations/acq_board_back_gen1.png
          :align: center
     - **Gen 1** Acquisition Boards have two power supply inputs, one on the Opal Kelly XEM6310-LX45 FPGA module and one on the main board. 
  


Hardware Differences
-------------------------

This table can help you understand the hardware differences that define each generation.

.. csv-table:: 
   :file: /_static/files/gen-hardware-diff.csv
   :widths: 16, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   

Drivers, Gateware and Software Compatibility
------------------------------------------------------

Different generations may require different drivers, gateware and software versions to operate, as per the table below.

.. csv-table:: 
   :file: /_static/files/gen-driver-gateware-software-diff.csv
   :widths: 16, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   

Functionality Differences
------------------------------------------------------

This table is meant to guide you in regards to functionalities across generations and differences you might notice during operation.

.. csv-table:: 
   :file: /_static/files/gen-functionality-diff.csv
   :widths: 16, 14, 14, 14, 14
   :header-rows: 1
   :stub-columns: 1
   

.. could add some styling to these tables using https://stackoverflow.com/questions/79112627/in-sphinx-how-do-i-style-a-csv-table
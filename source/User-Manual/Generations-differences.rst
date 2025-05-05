.. _gendiffs:

Differences Between Generations
=========================================

link to :ref:`Features <blah1>`.


The Acquisition Board design has evolved over the years to add features and replace obsoleted parts.

Although newer generations are backwards compatible and all generations generally work in the same
way, there are some important distinctions to consider. This page contains about information about
these distinctions.

Identify Your Acquisition Board
***************************************************************

Navigate the following tab set to identify which acquisition board you have. 

..  tab-set::

    .. tab-item:: Gen 3

        .. figure:: /_static/images/usermanual/generations/acq_board_back_gen3.png

        Gen 3 Acquisition Boards have a single power supply input on the Open Ephys FT600 USB
        board FPGA module and a Harp Clk output. The case has the 3d logo on the top.

    .. tab-item:: Gen 2

        .. figure:: /_static/images/usermanual/generations/acq_board_back_gen2.png

        Gen 2 Acquisition Boards have a single power supply input on the Open Ephys FT600 USB
        board FPGA module.         
        
    .. tab-item:: Gen 1

        ..  figure:: /_static/images/usermanual/generations/acq_board_back_gen1.png

        Gen 1 Acquisition Boards have two power supply inputs, one on the Opal Kelly
        XEM6310-LX45 FPGA module and one on the main board.

Acquisition Board Generation Differences
****************************************

This table summarizes the difference across generations:

..  csv-table:: 
    :file: /_static/files/gen-data.csv
    :widths: 1, 1, 1, 1, 1
    :header-rows: 1
    :stub-columns: 1

|
|
|

.. Proposal for organizing the above table: 
.. - features
.. - software compatibility
.. - latest gateware and drivers
.. - visual differences
.. - hardware differences

+------------------------------+-------------+-------------+-------+-------+
| Acquisition Board Generation | Gen 0       | Gen 1       | Gen 2 | Gen 3 |
+==============================+=============+=============+=======+=======+
| ..  _blah1:                                                              |
|                                                                          |
| *Features*                                                               |
+------------------------------+-------------+-------------+-------+-------+
| **Channel Count**            | 256         | 512         | 512   | 512   |
+------------------------------+-------------+-------------+-------+-------+
| **Commutator Capable**       | No          | No          | No    | Yes   |
+------------------------------+-------------+-------------+-------+-------+
| **Streams Orientation Data** | No          | No          | No    | Yes   |
+------------------------------+-------------+-------------+-------+-------+
| **Analog Inputs**            | ±5V or 0–5V | ±5V or 0–5V | ±5V   |       |
+------------------------------+-------------+-------------+-------+-------+
| *Software Compatibility*                                                 |
+------------------------------+-------------+-------------+-------+-------+
| **Open Ephys GUI**           | Yes         | Yes         | Yes   | v1.0+ |
+------------------------------+-------------+-------------+-------+-------+
| ...                          | ...         | ...         | ...   | ...   |
+------------------------------+-------------+-------------+-------+-------+

.. could add some styling to these tables using https://stackoverflow.com/questions/79112627/in-sphinx-how-do-i-style-a-csv-table


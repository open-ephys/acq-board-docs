.. _acquisitionsoftware:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Acquisition Software
***********************************

To process, record, and visualize data from the Acquisition Board, we recommend using one of the following applications:

1. The Open Ephys GUI
###################################
The **Open Ephys GUI** is an open-source, plugin-based application built specifically for acquiring extracellular electrophysiology data, available for download `from the Open Ephys website <https://open-ephys.org/gui>`_. The GUI has its own `documentation site <https://open-ephys.github.io/gui-docs/>`_.

2. Bonsai
###################################
Alternatively, you can use **Bonsai**, available for download `here <https://bonsai-rx.org/>`_. Bonsai is a visual reactive programming language, that can be used to acquire data from many different tools, including the Open Ephys Acquisition Board. You can insert a 'Rhd2000EvalBoard' Node into your Bonsai workflow. Right-click on this node to select what data to visualise (e.g. Ephys, inputs, Auxiliary channels) and add a MatrixWriter (configuring the path to end in '.bin') to save your data.


Which to choose?
###################################
The Open Ephys GUI is the most straightforward option for recording and visualizing electrophysiology data, as it has many plugins that were specifically developed for this purpose. 

Bonsai is worth trying out if you have a setup with multiple behavioural cameras or other data streams that need to be combined to deliver closed-loop feedback.

Bonsai and the Open Ephys GUI can be used combination, for example if you’re performing closed-loop feedback in Bonsai, but want to visualize your data in the Open Ephys GUI. Check out the `Ephys Socket Plugin <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Ephys-Socket.html>`_ for more information on this.

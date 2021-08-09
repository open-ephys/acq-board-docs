.. _acquisitionsoftware:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Acquisition software
***********************************

To acquire with the Open Ephys board, you can use:


1. The Open Ephys GUI
###################################
Available for download `here <https://open-ephys.org/gui>`_. The GUI is an open-source, plugin-based application built specifically for acquiring extracellular electrophysiology data. The GUI has its own `documentation site <https://open-ephys.github.io/gui-docs/>`_.

2. Bonsai
###################################
Alternatively, you can use `Bonsai, available here <https://bonsai-rx.org/>`_. Bonsai is a visual reactive programming language, that can be used to acquire data from many different tools, including the Open Ephys Acquisition Board. You can insert a 'Rhd2000EvalBoard' Node into your Bonsai workflow. Right-click on this node to select what data to visualise (e.g. Ephys, inputs, Auxiliary channels) and add a MatrixWriter (configuring the path to end in '.bin') to save your data.


Which to choose?
###################################
The OE GUI is probably the most straightforward option if you want to record and visualise electrophysiology data, as it has many plugins that were specifically developed for this purpose. Learning how to work with Bonsai can be difficult at first, but because it can handle many types of data, it may be worth trying out if you have a setup with e.g multiple behavioural cameras or other datastreams to synchronize.
Bonsai and the Open Ephys GUI can be combined, for example if you’re performing closed-loop feedback in Bonsai, but want to visualize your data in the Open Ephys GUI- check out the `Ephys Socket Plugin <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Ephys-Socket.html>`_.

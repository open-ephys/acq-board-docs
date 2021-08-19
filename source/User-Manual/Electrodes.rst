.. _selectingelectrodes:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Compatible electrodes
***********************************
.. will refer to skillhub for more general info on electrodes

The neuronal signals are first detected by the electrode, which directly interfaces with the tissue we are recording from. This initial signal is very small and analog, which means it is sensitive to interference from electrical noise. Because of this, the distance between the electrode and the headstage is crucial, and must be kept as short as possible. The headstage will filter, amplify, and digitize the signal. After that point, the signal is far more robust and protected, and the length of wires becomes less critical.

Several different types of electrode are compatible with the Open Ephys acquisition board. For any electrode, we must have a way of connecting the electrodes to the headstage. This is often done using an Electrode Interface Board (EIB), which has a connector compatible with the headstage on one end, and a board to which electrodes can be soldered or pinned.

When choosing electrodes, the considerations to keep in mind are:

Duration of experiment and behavior
###################################
How long will your recordings be, and will your animal be moving or performing other behaviors? Acute experiments under anaesthetic can be performed with a wide range of electrodes. However, if experiments are chronic and the animal has to live with electrodes implanted, we need to use a method that will impede their movement as little as possible. This is mainly done by keeping the weight and torque of the implant as low as possible. The torque (the rotational force) of the implant is kept low by making implants as short (close to the animal's head) as possible, and making sure that any wires or cables are thin, light, and do not pull or tug.

Tetrodes
###################################
.. will refer to skillhub for more general info on Tetrodes

Tetrode recordings with the Open Ephys Acquisition Board require matching the headstage with the correct EIB. Tetrodes are usually held in 'drives', which are implanted on the head of the animal and allow the lowering of tetrodes into the brain. The `Open Ephys ShuttleDrive <https://open-ephys.org/shuttledrive>`_ is a lightweight drive that can hold 16 tetrodes.

Silicon probes
###################################
Silicon probes can be used with the Open Ephys Acquisition Board and an Intan Headstage if they have an Omnetics connector, or an adaptor to the Omnetics connector. Alternatively, probes using a Hirose connector can be used with the `Open Ephys Low-profile Headstage <https://open-ephys.org/acquisition-system/low-profile-spi-headstage-64ch>`_.

.. note:: Won't work with Neuropixels!

.. _selectingelectrodes:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Compatible Electrodes
***********************************
.. will refer to skillhub for more general info on electrodes

The neuronal signals are first detected by the electrode, which directly interfaces with the tissue we are recording from. This initial signal is very small and analog, which means it is sensitive to interference from electrical noise. Because of this, the distance between the electrode and the headstage is crucial, and must be kept as short as possible. The headstage will filter, amplify, and digitize the signal. After that point, the signal is far more robust and protected, and the length of wires becomes less critical.

The Acquisition Board was designed with two types of electrodes in mind, tetrodes and silicon probes. For any electrode, we must have a way of connecting the electrodes to the headstage. This is often done using an Electrode Interface Board (EIB), which has a connector compatible with the headstage on one end, and a board to which electrodes can be soldered or pinned.

The type of electrodes you choose will depend on how long your recordings will be, and whether your subject will be moving or performing other behaviors. Acute experiments under anaesthetic can be performed with a wide range of electrodes. However, if experiments are chronic and the animal has to live with electrodes implanted, you will need to select electrodes that will minimally impede its movement. This is mainly done by keeping the weight and torque of the implant as low as possible. The torque (the rotational force) of the implant is kept low by making implants short (close to the animal's head), and making sure that any wires or cables are thin, light, and do not pull or tug.

Tetrodes
###################################
.. will refer to skillhub for more general info on Tetrodes

Tetrode recordings with the Open Ephys Acquisition Board require matching the headstage with the correct EIB. Tetrodes are usually held in "drives," which are implanted on the head of the animal and allow the tetrodes to be slowly lowered into the brain using screws. We recommend using the `Open Ephys shuttleDrive <https://open-ephys.org/shuttledrive>`_, a lightweight drive for mice that can hold up to 16 tetrodes.

Silicon probes
###################################
Silicon probes can be used with the Open Ephys Acquisition Board and an Intan Headstage if they have a 16-channel, 32-channel, or dual 32-channel Omnetics connector, or an adaptor to these Omnetics connector. Alternatively, probes using a Hirose connector can be used with the `Open Ephys Low-profile Headstage <https://open-ephys.org/acquisition-system/oeps-6570-6571?rq=low%20profile%20spi%20headstage>`_.

.. note:: Certain fully integrated silicon probes, such as Neuropixels, are not compatible with the Acquisition Board. This is because they use custom cables and a custom data transmission protocol. Neuropixels require a separate data acquisition system, such as the PXI-based system supplied by imec or `ONIX <https://open-ephys.github.io/onix-docs/>`_ from Open Ephys.

.. _commutators:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Commutators
***********************************

Commutators maintain a robust electrical connection between a rotating cable and a stationary cable. They are commonly used in neuroscience to prevent tether twisting during freely moving recordings of animals, since the animals move while wearing a headstage which is connected to a stationary acquisition system.

Commutators compatible with the Acquisition Board require a 12-pin connection for the SPI tethers. Most tethers have a polarized nano connector which mates directly with the connector on the SPI cables, but you can also interface with bare wires using an `RHD SPI cable adapter board <https://intantech.com/RHD_SPI_cables.html?tabSelect=RHDSPIadapter&yPos=48.88888931274414>`_. Because the commutator is an interconnect between the headstage and the Acquisition Board, a second tether is required: one from the headstage to the commutator, and one from the commutator to the Acquisition Board.

Typically, commutators are placed above the behavioral arena.

Open Ephys Torque-Free SPI Commutator
#######################################

Our torque-free SPI Commutator is a motorized commutator that corrects tether orientation using moment-to-moment information about the animal’s rotational state, instead of relying on tether torque measurement used in conventional active commutators. Open Ephys commutators rotate the tether before it's able to accumulate sufficient twist to induce torque on the animal head thereby reducing the mechanical load on the animal. This promotes more naturalistic animal behaviors.

.. figure:: ../_static/images/usermanual/commutators/OEPS-7761SPIC.jpg
   :width: 60%
   :align: center

   Open Ephys Torque-free Commutator - SPI

The inertial-measurement units (IMUs) embedded on :ref:`our 3D capable headstages <3dcap>` in combination with the 3rd Gen Acquisition Board provide real-time measurements of animal orientation which drive the commutator to compensate tether rotation automatically.

Other sensors present on commonly available headstages, such as a :ref:`3-axis accelerometer <acc>`, do not provide absolute orientation data and cannot be used to automatically compensate tether rotation with this commutator. However, this commutator can also receive commands from other real-time measurements of animal orientation such as video-based pose-estimation methods (e.g. DeepLabCut or SLEAP) to commutate headstages without 3D capabilities. Please refer to the `Commutators documentation site <https://open-ephys.github.io/commutator-docs/>`_ for further information.
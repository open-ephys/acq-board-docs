Automated Tether Commutation
============================

..  note::
    Following this tutorial requires a 3D capable headstage, an Open Ephys SPI commutator, and a 3D 
    capable data acquisition system (e.g. a Gen 3 Acquisition Board).

Most acquisition systems rely on a tether to transmit power and data between the headstage and the
data acquisition system. This can be problematic during freely behaving experiments because the
animal is liable to twist and tangle the tether while it moves around which can end up exerting
torque on the animal. This is mitigated by using a commutator, a device that untwists the tether as
the animal moves around while maintaining electrical continuity between the animal and data
acquisition system. This encourage more naturalistic behaviors.

This tutorial demonstrates how to automate commutation using a the Open Ephys GUI, a 3D-capable
headstage, and an Open Ephys SPI commutator. 

Hardware connections
#####################

#.  Refer to the :doc:`/Hardware-Guide/Cables` page to establish the following acquisition board connections:

    -   USB 3.0 connection between the acquisition board and the PC.

    -   +5V connection between the acquisition board and an AC power source.

#.  Follow the `SPI Commutator Connections section
    <https://open-ephys.github.io/commutator-docs/user-guide/mount-connect.html?commutator=spi#connecting>`__
    of the commutator docs to establish the following commutator connections:

    -   SPI connection between the commutator's stator and the acquisition board.

    -   SPI connection between the commutator's rotor and the 3D capable headstage.

    -   USB connection between the commutator and the PC.   

Install GUI and prepare signal chain
####################################

#.  `Install the Open Ephys GUI <https://open-ephys.github.io/gui-docs/User-Manual/Installing-the-GUI.html>`_ if you haven't already.

#.  Open the GUI. 

    ..  note::
        -   If this is your first time opening the GUI, you will be queried to load a default 
            signal chain. Choose the "Acquisition Board" signal chain.
        -   If the Open Ephys GUI already has a signal chain loaded you would like to save, 
            `do that <https://open-ephys.github.io/gui-docs/User-Manual/Exploring-the-user-interface.html#file>`_ 
            before proceeding because the next step overwrites any current signal chain.

#.  Download the following :download:`signal chain </_static/files/acq-board-commutator-signal-chain>`:

    ..  image:: /_static/images/tutorials/acq-board-commutator-signal-chain.png
        :alt: Acquisition Board Signal Chain for commutation

#.  `Open <https://open-ephys.github.io/gui-docs/User-Manual/Exploring-the-user-interface.html#file>`_ 
    the downloaded signal chain in the GUI.

    ..  tip::
        After opening the signal chain, confirm that "IMU" occupies one of the slots in headstage port indicator in the Acquisition Board processor. If "IMU" does not occupy one of those slots, the acquisition board did not detect a 3D-capable device.

#.  Refer to `Commutator Control plugin page
    <https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Commutator-Control.html>`_ 
    to configure the Commutator Control processor.

    -   The selected stream should correspond to a port that has a 3D capable headstage to it.

    -   The selected COM port should correspond to the one to which your commutator is connected. 

    -   For an off-the-shelf Open Ephys 3D capable headstage, adjusting the rotation axis is not
        necessary.

#.  Click the ▶ play button in the top-right corner of the GUI. The commutator should now follow the
    rotation of the headstage. 
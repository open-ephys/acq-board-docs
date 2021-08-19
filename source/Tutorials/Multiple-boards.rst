.. _usingmultipleboards:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Using multiple boards
***********************************

You can connect multiple acquisition boards to a single pc, and use two Rhythm nodes in the Open Ephys GUI. Keep in mind that the board order is somewhat arbitrary, as it depends on some usb descriptors. When you instantiate a Rhythm node it will use one of the boards, and the second the other, but loading the signal chain does not guarantee the nodes will be connected to the same boards. That is something you should manually check prior to acquisition.

Second, the two boards will act as independent, asynchronous devices. Their internal clocks are not synchronized and the small delays on start and stop commands might cause misalignments. You can use an external ttl trigger routed to both boards to be able to synchronize them.

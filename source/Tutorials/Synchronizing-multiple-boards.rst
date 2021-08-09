.. _usingmultipleboards:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Using multiple boards
***********************************

You can connect multiple acquisition boards to a single pc, and use two Rhythm nodes in the Open Ephys GUI. Keep in mind that the board order is somewhat arbitrary, as it depends on some usb descriptors. When you instantiate a Rhythm node it will use one of the boards, and the second the other, but loading the signal chain does not guarantee the nodes will be connected to the same boards. That is something you should manually check prior to acquisition.

Second, the two boards will act as independent, asynchronous devices. Their internal clocks are not synchronized and the small delays on start and stop commands might cause misalignments. You can use an external ttl trigger routed to both boards to be able to synchronize them.

Synchronizing multiple boards
###################################
Next board iteration should have a standard ribbon cable connector on (right or back) side that passes through a synchronization signal that is only enabled when the master system is acquiring data.
The slave systems should work as usual. Boards should be set to slave mode with a OkWireIn or equivalent via switch in the rhythm interface UI. Linking can be done with a ribbon cable with one twisted pair on the clk pins on the master side.

Pins:

GND
sync out - use to start and stop slave systems
sync in (out and in switched on master)
TTL ch8 out connected to D out  - use to send periodic sync codes every N seconds just in case we get worried about tiny clock drifts
TTL ch8 in, also just pulled from the D out channel (again, twist the pair on the master side so that we can send sync codes)

.. _synchronizingmultipleboards:
.. role:: raw-html-m2r(raw)
   :format: html

Synchronizing multiple boards
=================================================

Next board iteration should have a standard ribbon cable connector on (right or back) side that passes through a synchronization signal that is only enabled when the master system is acquiring data.
The slave systems should work as usual. Boards should be set to slave mode with a OkWireIn or equivalent via switch in the rhythm interface UI. Linking can be done with a ribbon cable with one twisted pair on the clk pins on the master side.

Pins:

GND
sync out - use to start and stop slave systems
sync in (out and in switched on master)
TTL ch8 out connected to D out  - use to send periodic sync codes every N seconds just in case we get worried about tiny clock drifts
TTL ch8 in, also just pulled from the D out channel (again, twist the pair on the master side so that we can send sync codes)
 


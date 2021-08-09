.. _measuringlatency:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Measuring latency
***********************************

Follow `this tutorial <https://open-ephys.github.io/gui-docs/Tutorials/Closed-Loop-Latency.html>`_ to measure the latency yourself.

The round-trip latency (acq board to computer back to acq board) is around 20 ms. This is sufficient for a variety of experiments involving closed-loop feedback. The main factor for the latency is the buffer size, as bigger buffers mean higher mean and higher variance of latency. This duration can be shortened by changing the size of the software buffer (down to approximately 10 ms, depending on processor speed).

To change the buffer size, click on the number of ms displayed in the status bar at the top of the Open Ephys GUI (to the right of the CPU load bar) and change the 'audio buffer size'. At some point the latency benefit becomes very small and the cpu load increases for smaller buffers, so it is worth experimenting to find the optimal value.

For experiments that require very low latencies, the `ONIX <https://github.com/open-ephys/onix-docs>`_ system is a better choice as it does not use USB communication but has a PCIe card directly in the acquisition computer.

.. _measuringlatency:
.. role:: raw-html-m2r(raw)
   :format: html

Measuring latency
=================================================

The round-trip latency (acq board to computer back to acq board) is around 20 ms—sufficient for a variety of experiments involving closed-loop feedback.
The main factor for the latency is the buffer size, bigger buffers mean higher mean and higher variance of latency.
This duration can be shortened by changing the size of the software buffer (down to approximately 10 ms, depending on processor speed).

To change the buffer size, click on the number of ms displayed in the status bar at the top (to the right of the CPU load bar) and change the 'audio buffer size'. At some point the latency benefit becomes very small and the cpu load increases for smaller buffers, so it is worth experimenting to find the optimal value.

USB3.0

Switching to USB 3 enables recordings of 512 channels and somewhat reduces latencies. See the rhythm module documentation for info on current software compatibility issues with USB3.

Nikolas Karalis ran some USB3 latency tests (link) pasted below:

As a test signal I feed a 10Hz sine wave, bandpass [8 12] and detect the peak. The event is sent to an arduino.

Using USB2 and default buffer (1024 samples), the latency is ~25 ms with very high variance.
Using buffers of 64 and 128 samples, you can get it down to 12 ms. For 32 channels and with a powerful laptop, you see some increase in the CPU usage (the before was minimal), but nothing dramatic.
USB3 improves things and can go down to 8 ms.

The smallest buffers can lead to crash and actually are not really improving the latency, so I think 64 or 128 samples provide a good balance.

I also tried with the -lowlatency and the -rt kernel at Ubuntu, in the hope things would be further improved, but they did not help. If anything they increase the variability.
However, I am not sure if perhaps I need to recompile the GUI using new headers to see any effect (that I did not try).

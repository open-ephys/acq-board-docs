.. _troubleshootingnoise:
.. role:: raw-html-m2r(raw)
   :format: html

Troubleshooting noise
=================================================

GND vs. REF on the Headstage
The gnd and ref connectors on the headstage aren't the same.
Most EIBs and adapters that we've been using tie them together, but it's still good to understand the difference.
(add more info here)

Extra shielding
A simple and fast solutions to some otherwise unsolvable noise might be to add even a partial faraday cage to your recording sites. This is true even with implants that already have a complete shielding - as long as part of your animal is not shielded, it can still pick up noise.

Line Noise caused by USB ground
Sometimes, the USB cable that connects the acquisition board to the PC (which is grounded to the building ground via the power supply) isn't good enough -  grounding the external shield of the USB cable that connects the FPGA to the computer can help.

Line noise caused by different power circuits
Make sure that all equipment, including the recording computer, is plugged into the same circuit and grounded to the same ground. This is especially crucial in buildings with separate building and earth grounds.
Be careful when bridging two ground circuits - sometimes they can carry a large potential difference. 

Dont use ungrounded laptops with no extra ground
If you're using the acquisition board with a laptop that's running off battery power, you will have a "floating" ground. This will cause your signals to look extremely noisy. To fix the issue, connect the ground of the acquisition board to whatever ground you're using for your experimental setup (perhaps a wall socket or a Faraday cage). You can either do this via the BNC connector (alligator clips work well for this), or by attaching a wire to one of the two dedicated screw terminals on the side of the board. The screw terminals are preferred because someday we may do something with the BNC. If you use the BNC, ground the shell of it to the wall, not the center pin. Connecting center pin of the BNC to ground will short your board and may fry the FPGA.



Beware of bad power supplies
Sometimes, aftermarket power supplies, mostly for laptops, but also for LED lights, or any other power brick, can cause a lot of line noise - try individually turning off equipment to isolate the offending one. 

Also, the supplied wall wart is not great at rejecting line noise - if 60Hz is a president issue, its worth trying powering the acquisition system from a high quality bench DC supply (5V) - this can significantly reduce noise in some cases.

Avoiding ground loops
add info here 


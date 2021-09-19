.. _assemblingtheioboard:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Assembling the I/O Board
***********************************

Required materials
###################################

Each board can serve as digital input, digital output, analog input, or analog output, but it can only perform one of those functions at any given time. You choose its function by plugging it in to one of the four HDMI connectors on the acquisition board. If you want to use all four functions at once, you'll need to build four boards.

For each I/O board you build, you'll need:

* One I/O board PCB. See below for instructions on how to order this.

* One thin, passive HDMI cable (type A to type A)

* Eight through-hole vertical BNC connectors ($2.40 each, DigiKey part #A97557-ND)

* One surface-mount HDMI connector ($0.73, DigiKey part #609-4614-1-ND cut tape)

Depending on what you're planning on connecting, you can also use screw terminals instead of (or in combination with) the BNC connectors. There are holes for 14 screw terminals, so you can solder on one each of 277-1279-ND and 277-1277-ND.

The following general lab supplies are necessary for assembly:

* Soldering iron (the thinner the better)

* Solder and flux

* 5-minute Epoxy (such as Z-poxy)

Obtaining the PCB
###################################

The easiest (and cheapest) way is to order the I/O board PCB it through the `Open Ephys store <https://open-ephys.org/acquisition-system/io-board-pcb>`__. However, if you made any changes to the design, you can follow the instructions below to order bare PCBs boards using Sunstone's `ValueProto <https://www.sunstone.com/pcb-products/pcb-manufacturing/valueproto>`__ service. If you have success with another company, please let us know!

#. Clone the `io-board <https://github.com/open-ephys/io-board>`__ repository on GitHub (or download it as a ZIP file).

#. On the ValueProto home page, type in 4.9" x 3.6" as the width and length

#. Type in the quantity you need and the shipping zip code, and check whether or not you want a "quick build" (1 week vs. 2 week turnaround time)

#. Click the "Upload File" button, and select "gerber.zip" from the io-board repository

#. The files for each layer might be recognized automatically. Double-check that it corresponds to the following:

    * Top silkscreen - :code:`gerber/io-board.slk`

    * Top solder mask - :code:`gerber/io-board.smt`

    * Top copper - :code:`gerber/io-board.top`

    * Bottom copper - :code:`gerber/io-board.bot`

    * Bottom soldermask - :code:`gerber/io-board.smb`

    * Plated holes - :code:`gerber/io-board.drd`

    * Tool size report - :code:`gerber/io-board.drl`

    *  Board outline - :code:`gerber/io-board.oln`

#. Click on the agreement checkbox, and then click the "Next step" button.

#. After looking at the information about drill sizes (nothing to worry about), agree to the terms and conditions and proceed to checkout.

With Sunstone, the cost should be about $80 for one board, or about $240 for four boards.


Putting it together
###################################

Solder the 8 BNC connectors into place on the I/O board. There are also holes for screw terminals (for example, Digikey 277-1279-ND) if you'd prefer that method of connection.

Solder the HDMI connector. This one's kind of tricky, so we recommend using the smallest soldering iron tip possible. If you accidentally solder two adjacent pins together, use flux to separate them. Remember to solder the through-hole connectors on the opposite side as well.

The soldering of the HDMI connectors is very similar to the method for hand-soldering omnetics connectors:

* Don't ever apply solder directly like you would for a through-hole part. This would apply way too much solder.

* Start by cleaning the board with ethanol if needed.

* Apply flux from a flux pen to the pads.

* Add a small drop of solder to the iron, and wipe it over the pads. This should result in a small amount of shiny solder on each pad, you should be able to see the solder form a pillow-like bulging shape. If the pads look/feel completely flat, like before you added solder, then you didn't add enough. If pads are connected with solder, you added too much.

* If too much solder was added, apply some more flux and de-solder with some copper solder wick. Be careful, it's pretty easy to remove too much/almost all solder this way.

* Once the pads are tinned, add some more flux, and place the HDMI connector in the mounting holes, and carefully move around so that the pads and feet are perfectly aligned.

* Now carefully tap the top of each foot/pin on the HDMI connector and push it down towards the pads. This should heat up the pin, and the solder, and you should feel how the melting solder allows the pin to be pushed down a bit more. it should also be possible to see the solder 'flowing' under the pin.

* Repeat the last step for all pins.

* To test if a pin is soldered correctly, you can carefully tap the sides of the pin with a needle/ forceps. if it moves ever so slightly, it is not soldered correctly.

* Only after all pins are soldered, turn the board over and solder the structural mounting holes by heating them and applying solder directly.

* Test all contacts by either connecting two I/O boards with a HDMI cable, or by plugging the board into a acquisition board and testing all TTL in channels.

* Alternatively, you can apply solder paste using a stencil, or even just by hand, and then use the heat gun to melt the solder onto the legs as described in the build guide for the acquisition board.

As a final step, place a drop of epoxy on the top of the HDMI connector, right where the plastic meets the metal. On some HDMI connectors, the plastic body has some wiggle room inside the metal shell. Because the metal shell is the structural component that is soldered to the PCB and the surface mount feet are embedded in the plastic, this can easily lead to broken connections. Epoxying the plastic to the metal shell in this way solves this issue. Don't use super glue or any runny glue that might get into the connector for this step.

The board can either be rack-mounted, placed on a flat surface (adhesive rubber feet are recommended), or placed in a case (let us know if you design one!).

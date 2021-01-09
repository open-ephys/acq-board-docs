.. _headstages:
.. role:: raw-html-m2r(raw)
   :format: html

Headstages
=================================================

Intan Headstages
####################


Channel mapping
----------------

Low-profile SPI headstage
##########################

This is an Open Ephys designed headstage, using an Intan chip. The main advantages of this headstage are:

It has a thin Intan SPI tether

It is compatible with all Intan/ Open Ephys Rhythm systems

It uses a Hirose connector to EIB, rather than an Omnetics connector, which greatly reduces cost. 

It weighs 0.92 g

Has 2 LEDs for tracking purpose

Primarily: the flat, round design means that the center of mass of the headstage is closer to the head of the animal. This cuts torque in half, reducing the impact on animal - mice can lower their heads and perform most licking/nosepoke paradigms. (Imagine wearing a heavy tall hat, and how that would influence your balance.) 

The channel map is available here. 

The standard Intan Headstage is on the left, the low-profile headstage on the right. 

Channel mapping
----------------

If you are using the low-profile Hirose SPI headstage, bought from Open Ephys Production site, use `this sheet <https://docs.google.com/spreadsheets/d/1WYDymxNqGRtFPxn69H9JzeMgePpXcFSPHiWJYBE0lu4/edit#gid=0>`__ to map your tetrodes to your software. It also includes the corresponding Hirose EIB (v.1.2) mapping. Using the classic Open Ephys Acquisition Board, channels will show up in software as if you sorted the sheet by the intan channel number.  


Samtec/Mill-max Headstage
###########################

PCB designs and manufacturing
Design files for a 32 channel RHD2132-based headstage using Samtec or Mill-Max 50 mil connectors can be found on the github (https://github.com/open-ephys/headstage/tree/master/1x32_Samtec). These headstages are designed so that the connector can soldered to the end of the PCB (avoiding the use of a surface mount 50 mil connector). Thus, the PCBs should be manufactured using slightly thinner than usual circuit board (~0.8 mm). A recommended manufacturer is the Fusion PCB service (http://www.seeedstudio.com/depot/fusion-pcb-service-2-layers-p-835.html), which can provide 10 PCBs for ~$2/ea. (Extra headstage PCBs may also be available from other users.)

The accelerometer, Intan RHD2132, and Omnetics connector should be soldered first. A solder mask stencil ($9 from http://www.oshstencils.com/) can be used to precisely locate solder paste, or it can be carefully applied with a fine tip. If a PCB oven is not available, a heat gun can be employed to reflow solder paste with satisfactory results. If using a heat gun, however, care must be taken not to damage the integrated circuits. Best practice is to observe the solder joints through a microscope while applying heat. The remaining components  (11 small (0603 or 0402) surface mount resistors, capacitors, and an LED) can then be soldered on by hand. Finally, the Samtec or Mill-Max connector can be soldered into place. A completed headstage is shown below. Note that after testing, the physical interface between PCB and Omnetics connector should be reinforced with epoxy.
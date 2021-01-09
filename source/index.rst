:notoc:

Open Ephys Acquisition Board
=================================================

.. **Date**: |today|

.. **Download documentation**: `PDF Version <open-ephys-documentation.pdf>`__ | `Zipped HTML <open-ephys-documentation.zip>`__

.. image:: _static/images/acquisition-board.jpg
  :alt: Photograph of the Open Ephys acquisition board

|

This is the new documentation site for the Open Ephys Acquisition Board, an open-source USB interface for acquiring extracellular electrophysiology data.

Previously, the Acquisition Boards's documentation lived on the `Open Ephys wiki <https://open-ephys.atlassian.net/wiki/spaces/OEW/pages/491597/Open+Ephys+Acquisition+Board>`__. We are planning to migrate all of the docs to this site over time.

The Acquisition Board was designed by neuroscientists to make their experiments more flexible and enjoyable. It provides a convenient USB interface between up to 8 headstages and a computer, and works equally well on macOS, Linux, and Windows. It also allows you to connect to up to 8 digital and analog inputs via I/O boards, each of which can provide up to 8 channels of digital or analog input. 

You can order a fully assembled Acquisition Board from the Open Ephys store, and headstages and cables can be purchased from Intan. You can also order an Open Ephys Starter Kit, which contains everything you need to get started (except for electrodes and an a computer).

Because all the designs are freely available, you can also build the Acquisition Board yourself. We estimate you'll spend about 2-3 days of work and about $1000. This includes the cost of the FPGA, the most expensive component. Follow the instructions :ref:`here <buildinstructions>` to learn how to build your own board.

A complete data acquisition system consists of the following hardware:

* An acquisition board, which you can either order or build yourself by following the :ref:`buildinstructions` section of this documentation.

* USB 3.0 cable

* 5V power supply

* At least one :ref:`headstage <headstages>` with an Intan RHD-series chip, which you can order from the Open Ephys store or the Intan website, or build yourself. Each headstage can handle 16 to 128 channels of neural input.

* One :ref:`cable <cables>` to connect each headstage to the acquistion board, which you can order from the Open Ephys store (as part of the starter kit) or the Intan website, or build yourself.

* (Optional) One or more :ref:`I/O boards <peripheraldevices>` for auxiliary (non-neural) signals. You . Each I/O board requires one HDMI cable to connect to the acquisition board.

* A :ref:`computer <computerhardware>` to run the software and interface with the rest of the system. The recommended configuration depends on the number of channels you plan to acquire simultaneously.

If you already have these components, follow the :ref:`quickstartguide` to learn how to start collecting data right away.

Otherwise, we recommend reading through the sub-pages to help you decide which components to buy.


.. raw:: html

    <div class="container">
        <div class="row">
            <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12 d-flex">
                <div class="card text-center intro-card shadow" style="width: 22rem;">
                <img src="_static/images/oe_logo_circle.svg" class="card-img-top" alt="Open Ephys logo" height="160">
                <div class="card-body flex-fill">
                    <h4 class="card-title">Quickstart Guide</h5>
                    <p class="card-text">Read this if you're just starting out.</p>

.. container:: custom-button

    :ref:`Getting started >><quickstartguide>`

.. raw:: html

                </div>
                </div>
            </div>
            <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12 d-flex">
                <div class="card text-center intro-card shadow" style="width: 22rem;">
                <img src="_static/images/noun_macbook.svg" class="card-img-top" alt="A laptop" height="160">
                <div class="card-body flex-fill">
                    <h4 class="card-title">Software Guide</h5>
                    <p class="card-text">How to install software.</p>

.. container:: custom-button

    :ref:`Installation >><acquisitionsoftware>`

.. raw:: html

                </div>
                </div>
            </div>
            <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12 d-flex">
                <div class="card text-center intro-card shadow" style="width: 22rem;">
                <img src="_static/images/noun_screwdriver.svg" class="card-img-top" alt="A screwdriver" height="160">
                <div class="card-body flex-fill">
                    <h4 class="card-title">Assembly Instructions</h5>
                    <p class="card-text">How to build it yourself.</p>

.. container:: custom-button

    :ref:`Build Instructions >><buildinstructions>`

.. raw:: html

                </div>
                </div>
            </div>
            <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12 d-flex">
                <div class="card text-center intro-card shadow" style="width: 22rem;">
                <img src="_static/images/noun_books.svg" class="card-img-top" alt="Some books" height="160">
                <div class="card-body flex-fill">
                    <h4 class="card-title">Tutorials</h5>
                    <p class="card-text">Guided tours on a variety of topics.</p>

.. container:: custom-button

    :ref:`Tutorials >><tutorials>`

.. raw:: html

                </div>
                </div>
            </div>
        </div>
    </div>

.. toctree::
    :hidden:
    :maxdepth: 2
    :titlesonly:

    User-Manual/index
    Build-Instructions/index
    Tutorials/index
    FAQ/index

:notoc:

*************************************************
Open Ephys Acquisition Board Documentation
*************************************************

.. **Date**: |today|

.. **Download documentation**: `PDF Version <open-ephys-documentation.pdf>`__ | `Zipped HTML <open-ephys-documentation.zip>`__\

*This is the current documentation site for the Open Ephys Acquisition Board, an open-source USB interface for acquiring extracellular electrophysiology data.*

.. image:: _static/images/acquisition-board.jpg
  :alt: Photograph of the Open Ephys acquisition board

|

The Acquisition Board was designed by neuroscientists to make their experiments more flexible and enjoyable. It provides a convenient USB interface between up to 8 headstages and a computer, and works equally well on macOS, Linux, and Windows. It also allows you to connect to up to 8 digital and analog inputs via I/O boards, each of which can provide up to 8 channels of digital or analog input.

How to get an OE Acquisition Board
#################################################
You can order an assembled Acquisition Board from `Open Ephys Production Site <https://open-ephys.org/acquisition-system/eux9baf6a5s8tid06hk1mw5aafjdz1>`_ , and headstages and cables can be purchased from Intan. You can also order an `Open Ephys Starter Kit <https://open-ephys.org/acquisition-system/starter-kit>`_, which contains everything you need to get started (except for electrodes and an a computer).

Because all the designs are freely available, you can also build the Acquisition Board yourself. We estimate you'll spend about 2-3 days of work and about $1000. Follow the instructions :ref:`here <buildinstructions>` to learn how to build your own board.

Getting Started
#################################################
Besides the acquisition board, you will need :ref:`these other components <acsystemparts>` to start collecting data. If you already have these components, follow the :ref:`quickstartguide` to learn how to start collecting data right away. Otherwise, we recommend reading through the sub-pages to help you decide which components to buy.

.. raw:: html

    <div class="container">
        <div class="row">
            <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12 d-flex">
                <div class="card text-center intro-card shadow" style="width: 22rem;">
                <img src="_static/images/oe_logo_circle.svg" class="card-img-top" alt="Open Ephys logo" height="160">
                <div class="card-body flex-fill">
                    <h4 class="card-title">User Manual: Quickstart Guide</h5>
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
                    <h4 class="card-title">User Manual: Software Guide</h5>
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

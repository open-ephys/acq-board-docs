:notoc:

.. title:: Home

.. **Date**: |today|

.. **Download documentation**: `PDF Version <open-ephys-documentation.pdf>`__ | `Zipped HTML <open-ephys-documentation.zip>`__\



.. image:: _static/images/acquisition-board.png
  :width: 80%
  :align: center
  :alt: Photograph of the Open Ephys Acquisition Board

The **Open Ephys Acquisition Board** is an open-source interface for acquiring up to 512 channels of extracellular electrophysiology data over a USB connection. 

You can order an assembled Acquisition Board from `Open Ephys Production Site <https://open-ephys.org/acquisition-system/acquisition-board>`_. You can also order an `Open Ephys Starter Kit <https://open-ephys.org/acquisition-system/starter-kit>`_, which contains everything you need to get started (except for electrodes and a computer).

Because all the designs are freely available, you can also build the Acquisition Board yourself. We estimate you'll spend about 2-3 days of work and about $1000. Follow the instructions `here <buildinstructions>` to learn how to build your own board.

Besides the acquisition board, you will need `these other components <acsystemparts>` to start collecting data. If you already have all of the necessary parts in your lab, follow the `quickstartguide` to learn how to start collecting data right away. Otherwise, we recommend reading through the sub-pages to help you decide which components to buy.

Key Specifications

* 4 headstage connections (up to 2 64-channel headstages per connection)
* Up to 512 channels
* USB data transmission
* 8 analog inputs
* 8 digital inputs
* 3D capabilities (from 3rd Generation onwards)
* Harp compatibility (from 2nd Generation onwards)

.. raw:: html
      
    <br>
    <div class="card-columns">
        <a class="reference internal" href="User-Manual/Quickstart-guide.html"><span class="std std-ref custom-card">
        <div class="card text-center intro-card">
            <img src="_static/images/oe_logo_circle.svg" class="card-img-top hover-zoom" alt="Open Ephys logo" height="100">
            <div class="card-body flex-fill">
                <h5 class="card-title">Quickstart Guide</h5>
                <p class="card-text">Read this if you're just starting out.</p>
            </div>
        </div>
        <a class="reference internal" href="User-Manual/Acquisition-software.html"><span class="std std-ref custom-card">
        <div class="card text-center intro-card">
            <img src="_static/images/noun_macbook.svg" class="card-img-top hover-zoom" alt="A laptop" height="100">
            <div class="card-body flex-fill">
                <h5 class="card-title">Software Guide</h5>
                <p class="card-text">How to install compatible software.</p>
            </div>
        </div>
        <a class="reference internal" href="Build-Instructions/index.html"><span class="std std-ref custom-card">
        <div class="card text-center intro-card ">
            <img src="_static/images/noun_screwdriver.svg" class="card-img-top" alt="A screwdriver" height="100">
            <div class="card-body flex-fill">
                <h5 class="card-title">Assembly instructions</h5>
                <p class="card-text">How to build it yourself.</p>
            </div>
        </div>
        <a class="reference internal" href = "Tutorials/index.html"><span class="std std-ref custom-card">
        <div class="card text-center intro-card">
            <img src="_static/images/noun_books.svg" class="card-img-top" alt="Some books" height="100">
            <div class="card-body flex-fill">
                <h5 class="card-title">Tutorials</h5>
                <p class="card-text">Guided tours on a variety of topics.</p>
            </div>
        </div>
    </div>

.. toctree::
    :hidden:
    :maxdepth: 2
    :titlesonly:

    User-Manual/index
    Hardware-Guide/index
    Tutorials/index
    Build-Instructions/index
.. QSTrader documentation master file, created by
   sphinx-quickstart on Wed Mar 15 09:57:57 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to QSTrader's documentation!
====================================

.. image:: https://travis-ci.org/mhallsmoore/qstrader.svg?branch=master
   :target: https://travis-ci.org/mhallsmoore/qstrader

.. image:: https://coveralls.io/repos/github/mhallsmoore/qstrader/badge.svg?branch=master
   :target: https://coveralls.io/github/mhallsmoore/qstrader?branch=master

.. image:: https://img.shields.io/badge/license-MIT%20License-blue.svg
   :target: https://github.com/mhallsmoore/qstrader/blob/master/LICENSE

.. image:: https://img.shields.io/badge/python-2.7%2C%203.4%2C%203.5-blue.svg
   :target: https://coveralls.io/github/mhallsmoore/qstrader?branch=master

QSTrader is an open source Python library for event-driven backtesting and live trading of the US equities markets with a focus on realistic simulation, modularity and extensibility. It is currently in an alpha state but is under heavy development.

QSTrader is designed for "power users" who want a broad framework to tie their systematic trading together, but which provides extensive customisation in the areas of market data handling, portfolio/order management, risk, position sizing and execution.

It has been designed both for a wide variety of use cases, from end-of-day retail traders through to small intraday quant funds trading at intraday frequencies.

The software is provided under a permissive commercial-friendly "MIT" license (:ref:`see below <ref-license>`).

Check out the :doc:`getting started guide </getting-started>`!

.. image:: https://s3.amazonaws.com/quantstart/media/images/qstrader-moving-average-cross-tearsheet.png

Features
--------

* **Event-Driven Architecture** - QSTrader is completely event-driven, allowing backtesting and live trading at a wide range of frequencies. The event-driven architecture allows "event generator" modules to be added easily, such as sentiment analysis signal generators, market data generators and risk manager generators.

* **Modular Design** - QSTrader ships with basic modules for backtesting and live trading. While these modules contain sensible, realistic defaults, they are designed to be fully extended and customised for those with more specific requirements.

* **Data** - QSTrader supports multiple data source formats, predominantly CSV files of the major vendors such as Yahoo Finance and DTN IQFeed. It supports tick-resolution (top of order book bid/ask) as well as OHLCV "bar" resolution data on various time scales. It is straightforward to add other vendors into the system by subclassing the PriceHandler module.

* **Backtesting** - QSTrader provides an efficient, out-of-the-box backtesting system for daily equities using Yahoo Finance data, with realistic position-handling and sensible defaults for transaction cost simulation. All behaviour is fully customisable allowing you to define your own transaction cost methodology.

* **Performance Metrics** - QSTrader supports both portfolio-level and trade-level performance measurement, displayed through a comprehensive visual "tearsheet" for a portfolio. Backtesting statistics can be exported and viewed through other reporting tools, such as Excel.

Getting Started
---------------

* The :doc:`QSTrader tutorial </getting-started>`
* The `original announcement post <https://www.quantstart.com/articles/Announcing-the-QuantStart-Advanced-Trading-Infrastructure-Article-Series>`_ on QuantStart.com

Installation
------------

QSTrader is in an early alpha state at the moment. It should only be used for **exploratory backtesting research**. The installation procedure is a little more involved than a standard Python package as it has not yet been added to the Python package repository.

**Ubuntu Linux is the recommended platform** on which to install QSTrader, but it will also work on Windows or Mac OSX under the `Anaconda distribution <https://www.continuum.io/downloads>`_.

The following steps will create a virtual environment directory with Python 3 and then activate the environment. Please change :code:`~/venv/qstraderp3` to your preferred virtual environment directory in the following::

    mkdir -p ~/venv/qstraderp3
    cd ~/venv/qstraderp3
    virtualenv --no-site-packages -p python3 .
    source ~/venv/qstraderp3/bin/activate

At this point it is necessary to use pip to install QSTrader as a library and then manually install the requirements. The following steps will take some time (5-10 minutes) as QSTrader relies on NumPy, SciPy, Pandas, Matplotlib as well as many other libraries and hence they will all need to compile::

    pip install git+https://github.com/mhallsmoore/qstrader.git
    pip install -r https://raw.githubusercontent.com/mhallsmoore/qstrader/master/requirements.txt

Now that the library itself and requirements have been installed it is necessary to create the default directories for the data and output. This will allow the example code to be run::

    mkdir -p ~/qstrader/examples ~/data ~/out

Now that the code has been installed and example directories created the :doc:`getting started guide </getting-started>` should be consulted on how to run some trading strategy backtests.

Development
-----------

* **Cross Platform** - QSTrader is written in the Python programming language for straightforward cross-platform support.

* **Testing** - QSTrader contains a suite of unit tests for the majority of its calculation code and these tests are executed upon every change to the code. Additional tests are constantly added for both current and new features.

* **Collaboration** - As QSTrader is open source many developers collaborate to improve the software. New features are added frequently. Any bugs are quickly determined and fixed.

*The project is constantly being developed so unfortunately it is likely that the current API will experience backwards incompatibility until a mature beta version has been produced.*

Contributors
------------

* `Michael Halls-Moore <https://github.com/mhallsmoore/>`_
* `Ryan Kennedy <https://github.com/ryankennedyio>`_
* `FemtoTrader <https://github.com/femtotrader>`_
* `Nick Willemse <https://github.com/nwillemse>`_

Sponsors
--------

.. image:: images/qs-logo.png
   :target: https://www.quantstart.com/

.. _ref-license:

Contact/Support
---------------

To report an issue with QSTrader or to suggest a feature please use the `issue tracker <https://github.com/mhallsmoore/qstrader/issues/>`_.

To interact with QSTrader developers email `mike@quantstart.com <mike@quantstart.com>`_ for a Slack invite.

License Terms
-------------

Copyright (c) 2015-2017 Michael Halls-Moore

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Trading Disclaimer
------------------

Trading equities on margin carries a high level of risk, and may not be suitable for all investors. Past performance is not indicative of future results. The high degree of leverage can work against you as well as for you. Before deciding to invest in equities you should carefully consider your investment objectives, level of experience, and risk appetite. The possibility exists that you could sustain a loss of some or all of your initial investment and therefore you should not invest money that you cannot afford to lose. You should be aware of all the risks associated with equities trading, and seek advice from an independent financial advisor if you have any doubts.

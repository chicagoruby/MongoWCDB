Chirp
=====

A trivial Twitter clone, example asynchronous Python / MongoDB app.

Prequisites
-----------

* Mac or Linux development machine or VM
* MongoDB: http://www.mongodb.org/downloads
* Git: http://git-scm.com/download
    * You probably already have it, try typing `git` on the command line
* Python 2.6 or 2.7: http://www.python.org/getit/releases/2.7.3/
    * You probably have this, too, try `python --version` on the command line
* Pip, the Python package manager:
  http://www.pip-installer.org/en/latest/installing.html
* Motor, my experimental asynchronous MongoDB driver for Tornado:
    * git clone https://github.com/ajdavis/mongo-python-driver
    * cd mongo-python-driver
    * git checkout motor

Installation
------------

Get the example app:

    git clone git://github.com/ajdavis/WindyCityDB.git
    cd WindyCityDB

Install required Python packages:

    pip install -I -r chirp.reqs

This installs:
* Tornado, an asynchronous Python web framework
* Tornadio, which implements websockets for Tornado
* Greenlet, a Python coroutine library needed for Motor

Usage
-----

Start MongoDB

    mkdir data
    mongod --dbpath data --logpath data/mongod.log --port 8000 --fork

Set your PYTHONPATH to include PyMongo and Motor:

    export PYTHONPATH=/path/to/mongo-python-driver

Start the Chirp application:

    python chirp.py

You should see log messages on your terminal indicating the web server has
started.

Visit http://localhost:8001/

Enter something in the 'New Chirp' box. Try it in two or three browser windows
at once!

In a new window, type `mongo` to open the MongoDB shell. Type `db.chirps.find()`
to see your collection of chirps.

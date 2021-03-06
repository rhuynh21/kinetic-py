Introduction
============
The [kinetic-protocol](https://github.com/Seagate/kinetic-protocol) python client.
Requires Python 2.7.3 or higher. Python 3.x is not supported.

Installing latest stable release
================================
    pip install kinetic


Installing from Source
======================

    git clone https://github.com/Seagate/kinetic-py.git
    cd kinetic-py
    git submodule update --init
    python setup.py develop

For devices with old firmware code:

    git checkout 0.7.3
    python setup.py develop

Running Tests
=============
The tests need a Kinetic device to run. You can use the simulator available at https://github.com/Seagate/kinetic-java.
To configure the test environment:

    export KINETIC_HOST=192.168.0.20
    export KINETIC_PORT=8123

Optionally you can point the tests to the simulator jar:

    export KINETIC_JAR=kinetic-simulator-<currentversion>-jar-with-dependencies.jar

Then to run the tests:

    python test/

Getting Started with the basic client
=====================================

```python
from kinetic import Client
c = Client('localhost', 8123)
c.put('message','hello world')
print c.get('message').value
```
Should print out _hello_ _world_

Troubleshooting during the installation
=======================================
On a brand new system, you might be missing a few things.
If you get an error saying setup tools not installed or missing.
Check the python [setuptools intallation guide](https://pypi.python.org/pypi/setuptools#installation-instructions).
If you needed to installed that, chances are you are missing some requirements to install and compile eventlet on your system.
On debian systems the quickest way is `sudo apt-get install python-eventlet`.


License
-------

This project is licensed under GNU Lesser General Public License, version 2.1
* [Markdown](LICENSE/LGPL2.1.md) version
* [Original](LICENSE/LGPL2.1.txt) version

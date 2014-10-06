LearnPyramid
============

Repository for Learning Pyramid Python Framework

**Assumes Ubunty Trusty**

$ git clone --recursive git://github.com/MarkCupitt/LearnPyramid.git

$ cd LearnPyramid

**Setup tools required**

$ sudo python ez_setup.py

**Install Virtual Environment as it is recommended by Pyramid**

$ sudo easy_install virtualenv

(do not use sudo to run the virtualenv script. It's perfectly acceptable (and desirable) to create a virtualenv as a normal user.)

$ export VENV=~/env
$ virtualenv $VENV

**Install Pyramid into teh Virtual Environment**

$ $VENV/bin/easy_install "pyramid==1.5.1"

*(If you see any warnings and/or errors related to failing to compile the C extensions, in most cases you may safely ignore those errors. If you wish to use the C extensions, please verify that you have a functioning compiler and the Python header files installed.)*

**Create a New Pyramid Project called MyProject**

$ $VENV/bin/pcreate -s starter MyProject

```
As a result of invoking the pcreate command, a directory named MyProject is created. 
That directory is a project directory. The setup.py file in that directory can be 
used to distribute your application, or install your application for deployment 
or development.

A .ini file named development.ini will be created in the project directory. You 
will use this .ini file to configure a server, to run your application, and to debug 
your application. It contains configuration that enables an interactive debugger and 
settings optimized for development.

Another .ini file named production.ini will also be created in the project directory. 
It contains configuration that disables any interactive debugger (to prevent 
inappropriate access and disclosure), and turns off a number of debugging settings. 
You can use this file to put your application into production.

The MyProject project directory contains an additional subdirectory named myproject 
(note the case difference) representing a Python package which holds very simple 
Pyramid sample code. This is where you'll edit your application's Python code and 
templates.
```


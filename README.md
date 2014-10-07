LearnPyramid.
================

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
** Installing MyProject for Development**
$ cd MyProject
$ $VENV/bin/python setup.py develop

**Running The MyProject Application**

Once a project is installed for development, you can run the application it represents using the pserve command against the generated configuration file. In our case, this file is named development.ini.

$ $VENV/bin/pserve development.ini

**Automatically forcing the Server to Reload Code after changes**

During development, it's often useful to run pserve using its --reload option. When --reload is passed to pserve, changes to any Python module your project uses will cause the server to restart. This typically makes development easier, as changes to Python code made within a Pyramid application is not put into effect until the server restarts.

$ $VENV/bin/pserve development.ini --reload

** Setting up the Debugging Toolbar**

If you click on the tool image shown at the right hand top of the page ("^DT"), you'll be presented with a debug toolbar that provides various niceties while you're developing. This image will float above every HTML page served by Pyramid while you develop an application, and allows you show the toolbar as necessary. Click on Hide to hide the toolbar and show the image again.

If you don't see the debug toolbar image on the right hand top of the page, it means you're browsing from a system that does not have debugging access. By default, for security reasons, only a browser originating from localhost (127.0.0.1) can see the debug toolbar. To allow your browser on a remote system to access the server, add a line within the [app:main] section of the development.ini file in the form debugtoolbar.hosts = X.X.X.X. For example, if your Pyramid application is running on a remote system, and you're browsing from a host with the IP address 192.168.1.1, you'd add something like this to enable the toolbar when your system contacts Pyramid:

```
[app:main]
# .. other settings ...

# By default, the toolbar only appears for clients from IP addresses
# '127.0.0.1' and '::1'.
# debugtoolbar.hosts = 127.0.0.1 ::1
debugtoolbar.hosts = 0.0.0.0/0 # This is dangerous and a Security Vunerability
```




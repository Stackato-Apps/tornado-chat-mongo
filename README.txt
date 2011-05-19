This is Facebooks's Tornado Chat demo app,
https://github.com/facebook/tornado/tree/master/demos/chat
which is adapted to use MongoDB for persistence.

Development
===========

    # install mongodb,tornado,pymongo,pycurl
    python app.py
    # visit http://localhost:8888/

Deployment (CloudFoundry)
=========================

First, prepare the CF server:

1. Install ActivePython to /opt/ActivePython-2.7
2. Install dependencies for this application (which should be
   automated as part of 'vmc push' in future)::

   $ sudo /opt/ActivePython-2.7/bin/pypm -g install tornado pymongo
   $ sudo /opt/ActivePython-2.7/bin/pip install pycurl

Then, push using ActiveState's fork of vmc; here's a sample session
(pay attention to 'Application Type' selection and service binding):

$ ~/as/vmc/bin/vmc push activechat
Would you like to deploy from the current directory? [Yn]: 
Application Deployed URL: 'activechat.vcap.me'? 
Detected a Unknown Application Type, is this correct? [Yn]: n
Select Application Type: (..., Sinatra, Node or Python) Python
Selected Generic Python Application
Memory Reservation [Default:64M] (64M, 128M, 256M, 512M or 1G) 
Creating Application: OK
Would you like to bind any services to 'activechat'? [yN]: y
The following system services are available::
1. mongodb
2. mysql
3. redis
Please select one you wish to provision: 1
Specify the name of the service [mongodb-dafcc]: 
Creating Service: OK
Binding Service: OK
Uploading Application:
  Checking for available resources: OK
  Packing application: OK
  Uploading (6K): OK   
Push Status: OK
Staging Application: OK                                                         
Starting Application: OK                               
$ 

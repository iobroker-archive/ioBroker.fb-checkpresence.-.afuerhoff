<h1>
    <img src="admin/fb-checkpresence.png" width="64"/>
    ioBroker.fb-checkpresence
</h1>

[![NPM version](http://img.shields.io/npm/v/iobroker.fb-checkpresence.svg)](https://www.npmjs.com/package/iobroker.fb-checkpresence)
[![Downloads](https://img.shields.io/npm/dm/iobroker.fb-checkpresence.svg)](https://www.npmjs.com/package/iobroker.fb-checkpresence)
[![Dependency Status](https://img.shields.io/david/afuerhoff/iobroker.fb-checkpresence.svg)](https://david-dm.org/afuerhoff/iobroker.fb-checkpresence)
[![Known Vulnerabilities](https://snyk.io/test/github/afuerhoff/ioBroker.fb-checkpresence/badge.svg)](https://snyk.io/test/github/afuerhoff/ioBroker.fb-checkpresence)

[![NPM](https://nodei.co/npm/iobroker.fb-checkpresence.png?downloads=true)](https://nodei.co/npm/iobroker.fb-checkpresence/)

**Tests:** Linux/Mac: [![Travis-CI](http://img.shields.io/travis/afuerhoff/ioBroker.fb-checkpresence/master.svg)](https://travis-ci.org/afuerhoff/ioBroker.fb-checkpresence)
Windows: [![AppVeyor](https://ci.appveyor.com/api/projects/status/github/afuerhoff/ioBroker.fb-checkpresence?branch=master&svg=true)](https://ci.appveyor.com/project/afuerhoff/ioBroker-fb-checkpresence/)

## fb-checkpresence adapter for ioBroker

The adapter checks the presence of family members over the fritzbox. 
You must fill in the name of the family member and the mac-address (or ip-address) of the used device. 
The comment is optional and you can enable or disable the family member. 
The datapoint is based on the member name.

## Fritzbox conditions

The used TR-064 interface to the fritzbox is described here: https://avm.de/service/schnittstellen/.
Following TR-064 functions are used:
* GetSpecificHostEntry 
* X_AVM-DE_GetSpecificHostEntryByIP (supported from 2016-05-18) -> is used to read the status of a member via the IP address
* GetHostNumberOfEntries
* X_AVM-DE_GetHostListPath (support from 2017-01-09) -> is used for member configuration
* GetSecurityPort

By default, the TR-064 interface is not activated. However, this can easily be changed via the 
FritzBox web interface. To do this log in into your FritzBox and ensure that the expert view is activated. 
Then you will find below "Home Network »Home Network Overview» Network Settings" the point 
"Allow access for applications". There you have to activate the checkbox and then restart the FritzBox once.
<img src="doc/access_settings_network.JPG"/>

## Configuration dialog

### Fritzbox IP-address, user and password
The configuration of ip-address, user and password is necessary to get the device data from the fritzbox. 
The password is encrypted and wasn't saved in clear text.

### Interval
The interval can be configured from 1 to 59 minutes. Normally a value of 1 minute is an optimal interval 
to read the fritzbox data.

### History adapter
Over the history adapter some values are calculated. You can choose, if the history,  the sql or the influxdb adapter is used.
The history adapter must be installed preliminary. 

### Dateformat
The date format mask options are described on this web page: https://www.npmjs.com/package/dateformat

### Family members
Without this configuration, the adapter does nothing. For a configured family member you must enter the Name,
the mac- or ip-address, a comment and if the member is enabled.

## Features

tbd.

## Changelog 

### 0.0.1
* (Achim Fürhoff) initial release
### 0.0.2
* (Achim Fürhoff) optimized features
### 0.0.3
* (Achim Fürhoff) guest feature added
### 0.0.4
* (Achim Fürhoff) calculation error resolved
### 0.0.5
* (Achim Fürhoff) configuration optimized
### 0.0.6
* (Achim Fürhoff) bug in json and html table resolved
### 0.0.7
* (Achim Fürhoff) Fix bug invalid date. Add debug information.
### 0.1.0
* (Achim Fürhoff) Influxdb added, debug information added


## License
MIT License

Copyright (c) 2019 Achim Fürhoff

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
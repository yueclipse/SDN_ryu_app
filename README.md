Overview
---------
This application introduced how ryu controller runs on fat tree topology and provides a simple method for load-balance.

Installaion
---------
* Python
* [mininet](http://mininet.org/download/)
* [Ryu](https://osrg.github.io/ryu/)

How to ping?
---------
If switch receives the packet and it has no corresponding flow table, it will direct the packet to the controller (called packet in).
Since the controller knows the entire topology including hosts (after the learning when controller boots), the controller will add flow table to each switch on the path to tell them how to transfer packets.

Traffic monitor
---------


Getting started
---------
**Before**

Install Ryu controller and mininet.

**Run the application**

**1. Generate Fattree topology**

    $ sudo {file_path}/fatTreeTopology.py

**2. Execute controller code**

    $ ryu-manager --observe-links {file_path}/fatTreeMultipath.py

**3. Test**

    minimet> h001 ping h005

[reference power point](https://goo.gl/eHKtGc)

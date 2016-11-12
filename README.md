Overview
---------
This application introduced how ryu controller runs on fat tree topology and provides a simple method for load-balance.

![alt tag](https://github.com/yueclipse/SDN_ryu_app/blob/master/image/fat tree.jpg)

Installaion
---------
* Python
* [mininet](http://mininet.org/download/)
* [Ryu](https://osrg.github.io/ryu/)

How to ping?
---------
If switch receives the packet and it has no corresponding flow table, it will direct the packet to the controller (called packet in).
Since the controller knows the entire topology including hosts (after the learning when controller boots), the controller will add flow table to each switch on the path to tell them how to transfer packets.

![alt tag](https://github.com/yueclipse/SDN_ryu_app/blob/master/image/ping.gif)

Traffic monitor
---------
To achieve load-balanced flows, the traffic monitor monitors each switch that controller can decide how to route the flow.

![alt tag](https://github.com/yueclipse/SDN_ryu_app/blob/master/image/traffic monitor.jpg)

**Result**

In a simple experiment, if all host ping to host 008, traffic monitor will help controller to decide a better path to the destination.

![alt tag](https://github.com/yueclipse/SDN_ryu_app/blob/master/image/result.jpg)

Run the application
---------
**Generate Fattree topology**

    $ sudo {file_path}/fatTreeTopology.py

**Execute controller code**

    $ ryu-manager --observe-links {file_path}/fatTreeMultipath.py

**Test by a simple ping**

    minimet> h001 ping h005

Reference links
---------
[OpenFlow](https://www.opennetworking.org/sdn-resources/openflow)
[OpenFlow based Load Balancing for Fat-Tree Networks with Multipath Support](http://users.cis.fiu.edu/~pand/publications/13icc-yu.pdf)

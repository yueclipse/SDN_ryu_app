Getting started
========
Before
--------
Install Ryu controller and mininet.

Run the application
--------
**1. Generate Fattree topology**

    $ sudo {file_path}/fatTreeTopology.py

**2. Execute controller code**

    $ ryu-manager --observe-links {file_path}/fatTreeMultipath.py

**3. Test**

    minimet> h001 ping h005

[reference power point](https://goo.gl/eHKtGc)

# Fork details  
![Not Python 3 Ready](https://img.shields.io/badge/python_3_ready-no-red?logo=python)  
This script relies a lot on old software. My goals are:
- rewrite for Python 3
- use bleak library instead of seemingly using a shell


## Requirements  
You need a recent version of bluez installed. You will also need the bleak library from PyPI.
Your Bluetooth adapter must support at least Bluetooth 4.0, although most already meet this requirement.


## Getting Started - Linux

```
$ lsusb
Bus 001 Device 005: ID 8087:0032 Intel Corp. AX210 Bluetooth
```


Turn MiP on and search for it (you'll probably have to sudo):

```
$ bluetoothctl
Agent registered
[bluetoothctl]> power on
Changing power on succeeded
[bluetoothctl]> scan le
SetDiscoveryFilter success
Discovery started
[CHG] Controller F4:46:37:D1:AD:B1 Discovering: yes
...
[NEW] Device B4:99:4C:59:F9:10 I am MiP
```

Grab the bluetooth address of MiP (in this case, B4:99:4C:59:F9:10). Time to start the script:
```
$ python3 src/examples/turtle_example.py -b B4:99:4C:59:F9:10
```

You should see MiP's chest light turn green when the Bluetooth connection is made. With this example, MiP will make a sound and move around.


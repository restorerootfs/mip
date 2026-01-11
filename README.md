# Fork details  
This script relies a lot on old software. My goals are:
- rewrite for Python 3
- use bleak library instead of seemingly using a shell


##Getting Started - Linux
You need a Bluetooth adapter supporting at least Bluetooth 4.0. Almost any modern adapter will work. Check with lsusb:

```
$ lsusb
Bus 001 Device 005: ID 8087:0032 Intel Corp. AX210 Bluetooth
```

You need a recent version of bluez installed. You will also need the bleak library from PyPI.


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


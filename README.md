# eSense BLE 
## Research on HID devices and their use case at North South University (NSU)

### Shell Script for reading IMU Data from the eSense BLE in-ears (PLUG&PLAY)

Requirements:
- Linux [Tested on Ubuntu 18.04]
- Bluetooth
- hcitool
- gattool

The commandline tools used come pre-packaged with installation of linux. Before running the code make sure your bluetooth device agent in detected by the OS. Run `hcitool dev` and `gatttool` from terminal to make sure they are present and bluetooth agent is detected.

Run:
```bash
git clone https://github.com/Soumic-Shekhar/eSense-Implementation.git
cd /path/to/eSense-Implementation/IMU_Data
./eSense.sh
```

### Python Script - Use accelerometer data to imitate HID input devices (mouse and keyboard)

#### esense_pexpect.py
Takes IMU Data from eSense using gatttool. Converts the raw accelerometer data to m/s<sup>2</sup>. Maps orientation of head (tilt) to mouse movement.
Logs acceleration in each axis with timestamp.

External modules used:
- [pexpect](https://pypi.org/project/pexpect/)
- [pynput](https://pypi.org/project/pynput/)

Run:
```bash
sudo python3 esense_pexpect.py
```

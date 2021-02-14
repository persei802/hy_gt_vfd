# hy_gt_vfd
This is a linuxcnc HAL component used to communicate with a Huanyang GT series VFD.
Prerequisite is minimalmodbus library.
See https://minimalmodbus.readthedocs.io/en/stable/
To use it, add the following line to your postgui hal file:

loadusr -Wn gt_vfd ./hy_gt_vfd.py -d /dev/ttyUSB0

Subsitute ttyUSB0 for whatever serial port your system uses. The modbus is typically provided by a USB dongle connected to the control computer.
A number of HAL pins must be connected to the main controller.
- spindle-on
- spindle-fb
- speed-cmd
- output-amps
- output-volts
- fault-info
- modbus errors

Most VFDs provide an AT_SPEED signal. If not, one can be created using the HAL near component.

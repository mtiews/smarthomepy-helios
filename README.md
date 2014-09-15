Helios Plug-in for Smarthome.py
-------------------------------

Plug-in for Helios ventilation systems using an USB RS-485 interface for [SmartHome.py](http://mknx.github.io/smarthome/).

Currently running for my Helios EC300 PRO using the USB-RS485 Interface EXSYS EX-1303.

Supported functions:

* Reading temperature values
* Turn ventilation system on/off
* Switching between summer/winter mode (bypass)
* Read/Write fan speed
* Read/Write bypass temperature
* Read/Write maximum/minimum fan speed.

Values will be read periodically from the ventilation system.

Plug-in can be used as command line tool (Python module argparse required).

Sample items.conf

```
[ventilation]
    [[power_state]]
        type = num
        helios_var = power_state 
        visu=yes
    [[bypass_disabled]]
        type = num
        helios_var = bypass_disabled 
        visu=yes
    [[outside_temp]]
        type = num
        helios_var = outside_temp 
        visu=yes
    [[incoming_temp]]
        type = num
        helios_var = incoming_temp 
        visu=yes
    [[inside_temp]]
        type = num
        helios_var = inside_temp 
        visu=yes
    [[exhaust_temp]]
        type = num
        helios_var = exhaust_temp 
        visu=yes
    [[fanspeed]]
        type = num
        helios_var = fanspeed 
        visu=yes
    [[bypass_temp]]
        type = num
        helios_var = bypass_temp 
        visu=yes
    [[max_fanspeed]]
        type = num
        helios_var = max_fanspeed 
        visu=yes
    [[min_fanspeed]]
        type = num
        helios_var = min_fanspeed 
        visu=yes
```

Configuration in SmartHome.py plugin.conf:

```
[helios]
    class_name = Helios
    class_path = plugins.helios
    tty = /dev/ttyUSB0
    cycle = 60 # default 300 seconds
```


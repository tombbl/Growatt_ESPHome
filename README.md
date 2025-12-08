## ESPHome configuration for Growatt SPF 5000 ES off-grid inverter
Please check [Growatt OffGrid SPF5000 Modbus RS485 RTU Protocol](https://www.scribd.com/document/563236514/Growatt-OffGrid-SPF5000-Modbus-RS485-RTU-Protocol) 
for more information about Growatt Modbus RS485 protocol and map of registers provided by the inverter.  

### Features
* Independent graphical ui with web server component
* Auto-discovery by Home Assistant
* All sensors and actions available for HA (easy use within automations)
* Plenty of inverter parameters available
* Auto time synchronization with Home Assistant
* LED conigured
* All inverter's states are mapped and reported correctly by sensor
* Once the dongle is flashed with ESPHome the updates can be easily done over WiFi

### Implemented holding registers:
```
Register  Description
      00  Standby On/Off and AC Output enable/disable
      01  AC output set
      02  Charge source set
      07  PV Input Model
      08  AC Input Model
      18  Output Voltage Type
      19  Output Frequency Type
      20  Over Load Restart
      21  Over Temperature Restart
      22  Buzzer Enable/Disable
      37  Battery low voltage switch to Uti (b2AC)
      38  AC charge current
      82  Battery voltage low cut-off
      95  AC switch to Battery (AC2b)
```

### Time synchronization with Home Assistant  
Realized in 2 manners:

* on-demand with **button** component
* auto sync at 11:55 AM/PM  

On synchronization the following holding registers are written:  

```
Register  Description
      45  System time Year
      46  System time Month
      47  System time Day
      48  System time Hour
      49  System time Minute
      50  System time Second
```

### Implemented input registers:
```
Register  Description
      01  PV Voltage
      03  PV Charge Power
      07  PV Current
      09  Output Active Power
      13  AC Charge Watt
      17  Battery Voltage (M3)
      18  Battery SoC
      19  Bus voltage
      20  AC Input Voltage
      21  AC Input Hz
      22  AC Output Voltage
      23  AC Output Frequency
      25  Inverter temperature
      26  DC-DC temperature
      32  PV temperature
      34  AC Output Current
      35  Inverting current
      36  AC Input Watt
      40  Fault bit
      41  Warning bit
      48  PV Energy Today
      50  PV Energy Total
      56  AC Charge Energy Today
      58  AC Charge Energy Total
      60  Battery Discharge Energy Today
      62  Battery Discharge Energy Total
      64  AC Discharge Energy Today
      66  AC Discharge Energy Total
      68  AC Charge Batt Current
      73  Battery Discharge Watt
      82  Inverter fan speed
```

### Screenshots
![web server component](https://raw.githubusercontent.com/tombbl/Growatt_ESPHome/0dac1202b7430d5de75a397b19860dbb710c2384/images/ha1.png  
![home assistant integration1](https://raw.githubusercontent.com/tombbl/Growatt_ESPHome/0dac1202b7430d5de75a397b19860dbb710c2384/images/ha2.png)  
![home assistant integration2](https://raw.githubusercontent.com/tombbl/Growatt_ESPHome/0dac1202b7430d5de75a397b19860dbb710c2384/images/webserver.png)  

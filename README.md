# ESPHome configuration example for Growatt SPF 3000/5000 ES inverter

## Holding registers covered:
1. As SELECT component:
* 00 Standby On/Off and AC Output enable/disable
* 01 AC output set
* 02 Charge source set
* 07 PV Input Model
* 08 AC Input Model
* 18 Output Voltage Type
* 19 Output Frequency Type
* 20 Over Load Restart
* 21 Over Temperature Restart

2. As NUMBER component
* 37 Battery low voltage switch to Uti
* 38 AC charge current
* 82 Bat voltage low cut-off
* 95 AC switch to Battery

## Time synchronization with Home Assistant
Uses holding registers: 45, 46, 47, 48, 49, 50.
* on-demand with BUTTON component
* auto sync at 11.55 AM/PM with TIME component

## Input registers covered:
TBD


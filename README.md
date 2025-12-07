## ESPHome configuration example for Growatt SPF 3000/5000 ES inverter

Please notice, the the *Programs* available from the inverter's user panel are not *Modbus registers* and the numbers are completely different .  

For the complete list of modbus registers please check [Growatt OffGrid SPF5000 Modbus RS485 RTU Protocol](https://www.scribd.com/document/563236514/Growatt-OffGrid-SPF5000-Modbus-RS485-RTU-Protocol) specification.  

### Holding registers as select component:  

| Reg. nr | Description |
|:------- |:------------|
|00|Standby On/Off and AC Output enable/disable
|01|AC output set |
|02|Charge source set |
|07|PV Input Model |
|08|AC Input Model |
|18|Output Voltage Type |
|19|Output Frequency Type |
|20|Over Load Restart |
|21|Over Temperature Restart |

### Holding registers as number component:  

| Reg. nr| Description|
|:--|:--|
|37|Battery low voltage switch to Uti
|38|AC charge current
|82|Bat voltage low cut-off
|95|AC switch to Battery

### Time synchronization with Home Assistant  
Realized in 2 manners:

- on-demand with **button** component
- auto sync at 11:55 AM/PM

Uses holding registers: 

| Reg. nr | Description |
|:------- |:------------|
|45 | System time Year
|46 | System time Month
|47 | System time Day
|48 | System time Hour
|49 | System time Minute
|50 |.System time Second


### Input registers covered:
| Reg. nr | Description |
|:------- |:------------|
|TBD||
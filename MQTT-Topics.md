# MQTT Topics for Panasonic Aquarea firmware

## Availability topic
panasonic_heat_pump/LWT will return Online when ESP is online, otherwise it will automatically return Offline

## Sensors:

ID | Topic | Response
--- | --- | ---
LOG1 | panasonic_heat_pump/log | Log of responses from pump
TOP1 | panasonic_heat_pump/sdc/Pump_Flow | Water pump flow, measured in L/min
TOP2 | panasonic_heat_pump/sdc/ForceDHW_State | DWW status (off - on - unknown)
TOP3 | panasonic_heat_pump/sdc/Power_State | Current Power state (off - on)
TOP4 | panasonic_heat_pump/sdc/OpMode_State | Current operating mode, valid responses are Heat, DHW, Cool, Auto, Heat+DHW, Auto+DHW, Cool+DHW
TOP5 | panasonic_heat_pump/sdc/Flow_Inlet_Temp | Inlet water temperature in °C
TOP6 | panasonic_heat_pump/sdc/Flow_Outlet_Temp | Outlet water temperature in °C
TOP7 | panasonic_heat_pump/sdc/Flow_Target_Temp | Outlet water target temperature in °C
TOP8 | panasonic_heat_pump/sdc/Compressor_Freq | Current compressor frequency
TOP9 | panasonic_heat_pump/sdc/Tank_Target_Temp | Tank temperature setpoint in °C
TOP10 | panasonic_heat_pump/sdc/Tank_Temp | Actual Tank temperature in °C
TOP11 | panasonic_heat_pump/sdc/Operations_Hours | Pump operating time in Hours
TOP12 | panasonic_heat_pump/sdc/Operations_Counter | Pump start/stop counter
TOP13 | panasonic_heat_pump/sdc/HeatShift_Temp | Heatshift (-5 to 5) or direct heat (20 to 50) temperature in °C
TOP14 | panasonic_heat_pump/sdc/Outside_Temp | Outside ambient temperature measured by compressor in °C
TOP15 | panasonic_heat_pump/sdc/Heat_Energy_Production | Thermal heat power produced in Watt
TOP16 | panasonic_heat_pump/sdc/Heat_Energy_Consumtion | Elektrical power consume at heat mode in Watt (steps of 200)
TOP17 | panasonic_heat_pump/sdc/Powerfullmode_Time | Powerfull state in minutes, valid responses are 0, 30, 60 or 90
TOP18 | panasonic_heat_pump/sdc/Quietmode_Level | Quiet mode state, valid responses are 0, 1, 2, 3
TOP19 | panasonic_heat_pump/sdc/Holidaymode_State | Holiday mode, valid responses are 84=Off and 100=On
TOP20 | panasonic_heat_pump/sdc/Valve_State | 3-way valve mode, valid responses are Room, Tank or Defrost
TOP21 | panasonic_heat_pump/sdc/Outside_Pipe_Temp | Outdoor pipe temperature used for defrost
TOP22 | panasonic_heat_pump/sdc/Tank_Heat_Delta | Tank delta K
TOP23 | panasonic_heat_pump/sdc/Heat_Delta | Heat delta K
TOP24 | panasonic_heat_pump/sdc/Cool_Delta | Cool delta K
TOP25 | panasonic_heat_pump/sdc/Quietmode_State | Current silent mode state ( ???? )
TOP26 | panasonic_heat_pump/sdc/Defrosting_State | Current defrost state ( ???? )
TOP27 | panasonic_heat_pump/sdc/Heat_Shift_Temp | Temperatur shift (-5 to 5) or direct heat temperatur (20 to 50)
TOP28 | panasonic_heat_pump/sdc/Cool_Shift_Temp | Temperatur shift (-5 to 5) or direct cool temperatur (?? to ??)
TOP29 | panasonic_heat_pump/sdc/HCurve_OutHighTemp | Target temperatur °C at lowest point of the heating curve (eg. 34)
TOP30 | panasonic_heat_pump/sdc/HCurve_OutLowTemp | Target temperatur °C at highest point of the heating curve (eg. 24)
TOP31 | panasonic_heat_pump/sdc/HCurve_OutsHighTemp | Lowest outsite temperatur of the heating curve (eg. -12)
TOP32 | panasonic_heat_pump/sdc/HCurve_OutsLowTemp | Highest temperatur of the heating curve (eg. 15)
TOP33 | panasonic_heat_pump/sdc/Roomthermostat_Temp | Remote control thermostat temp
*TOPxx* | panasonic_heat_pump/sdc/Evaporator_out_Temp | to decode
*TOPxx* | panasonic_heat_pump/sdc/Pump_operating_Point | to decode
*TOPxx* | panasonic_heat_pump/sdc/Fan_Speed | fan speed in 1/min
*TOPxx* | panasonic_heat_pump/sdc/Cool_Energy_Production | Thermal cool power produced in Watt
*TOPxx* | panasonic_heat_pump/sdc/Cool_Energy_Consumtion | Elektrical power consume at cool mode in Watt (steps of 200)
*TOPxx* | panasonic_heat_pump/sdc/DHW_Energy_Production | Thermal DHW power produced in Watt
*TOPxx* | panasonic_heat_pump/sdc/DHW_Energy_Consumtion | Elektrical power consume at DHW mode in Watt (steps of 200)

*In addition, a unique ID could be used for the device (eg. panasonic_heat_pump_ID_OF_HEATPUMP) to manage more then one device. Please check, this will change al our work behind mqtt.* 

## Commands:
Topic | Description | Values
--- | --- | ---
panasonic_heat_pump/SetHoliday | Set holiday mode on or off | 84 = Off, 100 = On
panasonic_heat_pump/SetQuietMode | Set quiet mode level | 0, 1, 2 or 3
panasonic_heat_pump/SetPowerfull | Set powerfull mode run time in minutes | 0, 30, 60 or 90
panasonic_heat_pump/SetShiftTemperature | Set heatshift or direct heat temperature | -5 to 5 or 20 to 50
panasonic_heat_pump/SetOpMode | Sets operating mode | Heat, Cool, DHW, AUto, Heat+DHW, Auto+DHW or Cool+DHW
panasonic_heat_pump/SetForceDHW | Forces DHW mode only | 1
panasonic_heat_pump/SetTankTemp | Set tank target temperature | 40 - 75
panasonic_heat_pump/SetCoolTemp | Set cooldown temperature | 5 - 20
panasonic_heat_pump/SetForceDefrost | Forces defrost routine | 1
panasonic_heat_pump/SetForceSterilization | Forces tank sterilization routine | 1

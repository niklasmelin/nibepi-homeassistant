# Integrate nibepi to Home Assistant
Tutorial on how to connect nibepi to Home Assistant to allow for monitoring and controlling
the Nibe heat pump from Home Assistant. It allows for monitoring of current values such as:
- utilization of electrical heater
- Warm water temperature
- Outdoor and indoor temperature sensors
- Condenser and evaporator temperatures
- Fan speed
- Pump frequency
- and many more things....

By attaching a Raspberry Pi with a Modbus HAT and a 12 V power HAT it can communicate with the Nibe heat pump over Modbus.
There are multiple ways to do this and check out the nibepi project for alternatives. This is my current installation:   
![raspberryPI](images/RaspberryPi-Zero_nibePi.png)

nibepi is a project found on [https://github.com/anerdins/nibepi](https://github.com/anerdins/nibepi) 
with a closed community on Facebook [https://www.facebook.com/groups/nibepi/](https://www.facebook.com/groups/nibepi/)
where you can as request to join. The community is a great place for questions and share your experiences primarily
with nibepi. The base of many examples in this tutorial has been found in posts and comments in the Facebook group.
Where attribution of code is missing, please point me in the right direction so that this can be corrected.

## Table of contents
1. [Prerequisites](#prerequisites)
2. [Configuration](#configuration)
   1. [nibepi - mqtt settings to connect to mqtt broker](nibepi-settings-mqtt.md)
   2. [nibepi - publish registers to mqtt](nibepi-registers-mqtt.md)
   3. [Home Assistant - Add integration - MQTT](HomeAssistant-mqtt-settings.md)
   4. [Home Assistant - Add HACS custom Frontend components](HomeAssistant-HACS-Add_Components.md)
3. Home assistant - Examples to monitor and control your Nibe heat pump
   1. [Status image with temperature control](configs/status_image_with_temperature_control/status_image_with_temperature_control.md)
   2. [Heat pump schematics with sensor information](configs/heat_pump_schematics_with_sensors/Hassio_Heat_pump_schematics_with_sensors.md)
   3. [Heat pump fan control](configs/fan_control/Hassio_Fan_control.md)
   4. [Heat pump hot water mode control](configs/hot_water_mode/Hassio_Hot_water_mode.md)

## Prerequisites
This tutorial assumes the following:
- A working nibepi connected to your heat pump and reachable on your local network
- A working [mqtt server/broker](https://mqtt.org/). Either in Home Assistant as [add-on (instructions link)](https://github.com/home-assistant/addons/blob/174f8e66d0eaa26f01f528beacbde0bd111b711c/mosquitto/DOCS.md#how-to-use) or stand alone.
- A working [Home Assistant](https://www.home-assistant.io/) system
- The [HACS-plugin](https://hacs.xyz/) installed in Home Assistant.


## Configuration
- Configuration:  _nibepi_ - Connection to mqtt broker  
  The required setting to allow for _nibepi_ to publish and to subscribe to messages on the mqtt broker.  
  [nibepi - Connect to mqtt broker](nibepi-settings-mqtt.md)
   

- Configuration:  _nibepi_ - Registers to publish to mqtt broker  
  Select which register to publish and subscribe to on the mqtt broker. Only selected registers will be
  available in _Home Assistant_.  
  [nibepi - Publish registers to mqtt](nibepi-registers-mqtt.md)   


- Configure _Home Assistant_ - Integration mqtt  
  For _Home Assistant_ to be able to subscribe and to publish messages to the mqtt broker an integration must be
  added and configured.  
  [Home Assistant - Add integration - MQTT](HomeAssistant-mqtt-settings.md)

## SSH connection
You can connect to you NibePI using SSH with the user pi and password nibe.

## Contribution
You are most welcome to add more examples on how the _nibepi_ integration can be utilized with Home Assistant to create 
or enhance smart functions.
- For simpler things, the report Issue function here might be sufficient.
- For more advanced things, please fork the repository and make a pull request.

# air_quality_sensor

## Requirements
The device mainly needs to measure temperature, humidity, CO2 levels, TVOC levels and LPG

### SCD41
This sensor takes care of temperature, humidity and CO2 levels.
More information will be added further down development.

### SGP41
This sensor takes care of TVOC levels and additionally NOx levels.
More information will be added further down development.

### MQ-6
This sensor takes care of LPG gasses.
Since both this sensor and the MQ-7 only run of 5v I've added a solder jumper between the MCU and the battery, to ensure that the battery is only used if these two sensors are not connected. This jumper must be shorted for the device to run on battery power.
More information will be added further down development.

### MQ-7
Added this sensor for carbon monoxide measurements. 
It has the same symbol and footprint as the MQ-6 sensor. It is also wired equally.

### Display connector
I've also added a FFC connector to add a TFT display.

### Seed Studio's ESP32-C6
This will be the main MCU for the device. Mostly chosen because it is what I had on hand, but also because of it's flat underside, enabling it to be SMD mounted. It also has great connectivity, both in GPIO pins and wireless (WiFi, BLE and Zigbee).

### To be implemented
Looking up ways to isolate the temperature sensor. 
feeding the MQ-x sensor with the battery and using a shorter battery (18xxx).

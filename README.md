# Description
This project consists on the full development of an embedded system, with the purpose of measuring air quality.
### Included in this project:
- PCB design and schematics
- Firmware for the device
- Communication with other devices
- Integration with external systems (graphical interface)

# Characteristics
- The device will be able to measure the following:
  - Temperature
  - Humidity
  - CO2 levels
  - TVOC
  - NOx
  - LPG
  - CO
- Wireless connectivity (WiFi, BLE or LoRa)
- Modularity. Ideally you should be able to use only the sensors you need.

# Hardware
## ESP32-C6
The device is built around Seed Studio's ESP32-C6 dev-board, this simplifies the PCB design. Given its size and extensive set of features, it gives the project tons of flexibility.

## Sensors
### SCD41
Sensirion's SCD41 provides temperature, humidity and CO2 measurements with enough precision for home use. It also includes calibration for the CO2 measurements.
### SGP41
Also from Sensirion, but it measures TVOC and NOx. Temperature from the previous sensor can be used to calibrate the SGP41.
### MQ-6
Manufactured by SparkFun, this is a LPG sensor.
### MQ-7
Once again manufactured by SparkFun, this senses Carbon Monoxide.

## Display
The design features a FFC connector to add a TFT display.

## Power
When powered by the ESP's USB-C connector, the ESP board itself provides power to every component.
When a one cell battery pack is used (ie. 18650 or 18300 Li-ion), components powered by 3V3 are still managed by the ESP. However, sensors requiring 5V are powered through a Boost Converter that transforms the batteries voltage to a steady 5V.

## Interfaces
The sensor SCD41 and SGP41 communicate over I2C, both MQ-x sensors use an analog signal and the display will be set up to use 4-wire SPI.

# PCB
The current version of the project features a 2 layer PCB, with the bottom one being a ground plane.
The large space in the middle is there to give space for a 18650 or 18300 battery (depending on which sensors are installed). It also serves to distance the SCD41 sensor from heat sources, such as the MCU or the boost converter.
The SCD41 sensor is excluded from the ground plane and placed within an isolation island, for better accuracy in the temperature measurements

# Firmware
// Yet to be implemented

# Images

# Documentation
All the documentation used for the design of the PCB can be found at `./air_quality_pcb/docs/`

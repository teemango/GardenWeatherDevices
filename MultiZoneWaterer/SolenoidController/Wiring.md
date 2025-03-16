#  Wiring for A Solenoid Controller for Two Watering Zones

## Mosfet pin connections
Below is a photo of the IRLB8721 mosfet, illustrating which pins correspond to gate, drain, and source.

![image](https://github.com/user-attachments/assets/2a016928-8389-4716-b39c-6293ca436a62)


## Soil moisture sensor
| Mosfet pin     |      |  Wemos Lolin32   |
| :---:          |:---: |  :---:          |
| GND            | ---> |  GND            |
| VCC            | ---> |  9             |
| Data           | ---> |  A0             |

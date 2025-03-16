#  Wiring for A Solenoid Controller for Two Watering Zones

## Mosfet pin connections
Below is a photo of the IRLB8721 mosfet, illustrating which pins correspond to gate, drain, and source. You will need one mosfet for each of the two watering zones

![image](https://github.com/user-attachments/assets/2a016928-8389-4716-b39c-6293ca436a62)


## Soil moisture sensor for watering zone 1

| Mosfet pin     |      |  Connection point(s)                               |  
| :---:          |:---: |  :---:                                             |
| Gate           | ---> |  pin 32 of Wemos lolin, through a 100 ohm resistor | 
| Drain          | ---> |  to the ground side of your power source           |
| Source         | ---> |  GND of Wemos Lolin32                              |

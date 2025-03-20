#  Wiring for A Solenoid Controller for Two Watering Zones

## Mosfet, solenoid, and solenoid power connections
Below is a photo of the IRLB8721 mosfet, illustrating which pins correspond to gate, drain, and source. You will need one mosfet for each of the two watering zones

![image](https://github.com/user-attachments/assets/2a016928-8389-4716-b39c-6293ca436a62)


### Mosfet connections for watering zone 1

| Mosfet pin     |      |  Connection point(s)                                |  
| :---:          |:---: |  :---:                                              |
| Gate           | ---> |  pin 32 of Wemos lolin, through a 100 ohm resistor that is also connected to ground via a 1K resistor* | 
| Drain          | ---> |  to the ground side of solenoid 1                   |
| Source         | ---> |  GND of Wemos Lolin32                               |
|                |      |  *Connect one leg of a limiting resistor (I use a 100 ohm resistor) to pin 32 of the lolin and the other leg of the resistor to the gate pin of the mosfet. Additionally connect one leg of a 1K ohm resistor to the leg of the 100 ohm resistor furthest away from the lolin and the other leg of the 1K resistor to ground. The 100 ohm resister protects the gate pin from any power surges. The 1K resistor provides a path to ground so that the gate pin does not "float" (to make sure the solenoid never gets powered on when it is supposed to be off).                               |

                                                                              
### Mosfet connections for watering zone 2

| Mosfet pin     |      |  Connection point(s)                                |  
| :---:          |:---: |  :---:                                              |
| Gate           | ---> |  pin 33 of Wemos lolin, through a 100 ohm resistor that is also connected to ground via a 1K resistor* | 
| Drain          | ---> |  to the ground side of solenoid 2                   |
| Source         | ---> |  GND of Wemos Lolin32                               |
|                |      |  *Connect one leg of a limiting resistor (I use a 100 ohm resistor) to pin 32 of the lolin and the other leg of the resistor to the gate pin of the mosfet. Additionally connect one leg of a 1K ohm resistor to the leg of the 100 ohm resistor furthest away from the lolin and the other leg of the 1K resistor to ground. The 100 ohm resister protects the gate pin from any power surges. The 1K resistor provides a path to ground so that the gate pin does not "float" (to make sure the solenoid never gets powered on when it is supposed to be off).                              |

Reistance values for the limiting resistor and path to ground may vary depending on your source of info. The 100 ohm (limiting resistor) and 1K ohm (for path to ground) resistors have worked well for me. Keep in mind that the limiting resistor needs to allow enough voltage to reach the gate pin of the mosfet for it to turn on. For the path to ground, too much resistance will not allow for a path to ground (which could cause the solenoid to stay on when it is supposed to shut off) while not enough resistance (such as that with a straight wire connection to ground with no resistor) will result in the gate never receiving enough voltage for the solenoid to turn on. 

### Solenoid flyback diodes
To protect the solenoid from power spikes, connect a diode acrosss the terminals of the solenoid. This can be done by connecting wires to the solenoid that have been crimped into female quick disconnect terminals; crimp terminals often have a hole that makes a convenient place to insert a leg of a diode for soldering. It does not matter which way you orient the diode across the solenoid termminals, but once you solder a diode across the terminals of a solenoid, whichever solenoid terminal is connected to the side of the diode with the white stripe becomes "positive" and the opposite side "ground". 

### Power source to solenoids
The 12 v DC solenoid will open with a DC power source (adaptor plug or battery) that supplies 6 v (in my experience 5 v is not enough but 6 v usually is; check to make sure if in doubt) to 12 v.  

| Power source      |      |  Connection point(s)                                |  
| :---:             |:---: |  :---:                                              |
| Positive terminal | ---> |  to the positive side of each solenoid             |
| Ground terminal   | ---> |  to GND of the Wemos Lolin                          |

For a permanent build, solder components onto a solderable breadboard, with screw terminals as a way to connect wire cable from solenoids and a solenoid power source to the board. The diagram below illustrates this concept. In your final build, place components closer together on the board to make room for a LoRa module that will receive soil moisture readings from the soil moisture transmitter in each of your two watering zones. The diagram below was created with Cirkit Designer, which by default makes ground wires blue; in my actual build, I used black wires for ground (negative) and red wires for power (positive) connections
                                                                            
![SolenoidControllerMosfetConnections](https://github.com/user-attachments/assets/2b1b2eca-ec02-43f1-bff3-381cfd3b0e89)

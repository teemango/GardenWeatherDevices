# Wiring  
#### Connections between components and the Arduino Pro Mini (3.3v) microcontroller

## Soil moisture sensor
| Soil sensor    |      |  Arduino Nano   |
| :---:          |:---: |  :---:          |
| GND            | ---> |  GND            |
| VCC            | ---> |  D9             |
| Data           | ---> |  A0             |

##Solenoid and diode
Solder a 1N4007 diode between the the two terminals on the solenoid. The diode will have a white stripe on one end. It doesn't matter which terminal of the solenoid is closest to the white strip, but once you solder the diode to the solenoid terminals, or wires connected to the terminals, the terminal closest to the white stripe becomes the positive terminal of the solenoid. 

See this instructible for photos and more details on how to connect the diode to the solenoid, as well as other connections: https://www.instructables.com/Controling-a-solenoid-valve-with-an-Arduino/

## Mosfet, battery, and Attiny85
I used an [IRLB8721](https://www.digikey.com/en/products/detail/infineon-technologies/IRLB8721PBF/2127670) logic-level (meaning it can be turned off/on with 3.3v or 5v microcontrollers) mosfet and a 18650 3.7 volt lithium ion battery. When fully charged, the battery will be close to 4.2 v. Ideally, one should provide 3.3 v to the Pro Mini, which is possible via a voltage regulator. I omitted the voltage regulator, however, in an effort to conserve battery power and in light of the fact that I have not had any problems doing so.

In making the connections below it is helpful to understand how pins are designated on the Attiny85 microcontroller. An Attiny85 has 8 pins as indicated [here](https://solderingmind.com/attiny85-microcontroller-working-pin-out-and-programming).

1. Connect the Gate pin of the mosfet to pin PB3 of the Attiny85. To make sure the Pro Mini stays off when it is supposed to, you can connect one leg (wire) of a 100 ohm resistor to the Gate pin of the mosfet and the other leg (wire) of the 100 ohm resistor to ground (PB5) of the Attiny85. 
2. Connect the Drain pin of the mosfet to a ground (GND) pin of the Arduino Pro Mini.
3. Connect the Source pin of the mosfet to ground (PB5) of the Attiny85.
4. Connect the negative (black; ground) terminal of the battery to the ground (PB5) pin of the Attiny85.
5. Connect the positive (red; power) terminal of the battery to the VCC pin of the Attiny85 and to the 3V3 pin of the Arduino Pro Mini. This works out fine with a 3.7v 18650 battery (or two of these batteries connected in parrallel--so that voltage stays the same) since it will not overpower either device.

See the photo below to identify the Gate, Drain, and Source pins on the mosfet. Note that the photo identifies the pin with the black portion (with writing) of the mosfet facing you.

![MosfetLabeled](https://github.com/user-attachments/assets/84e01369-fc0b-42bd-acd3-579d18a86e7e)

## Arduino Pro Mini and LoRa RFM95 transceiver

#### LoRa transceiver
| LoRa           |       | Arduino Pro Mini  |
| :---:          | :---: | :---:             |
| GND            |  ---> | GND               |
| VCC/VIN        |  ---> | 3v3               |
| D0/GO          |  ---> | 3                 |
| SCK            |  ---> | 13                |
| MOSI           |  ---> | 11                |
| MISO           |  ---> | 12                |
| CS/NSS/ss      |  ---> | 4                 |         

Make sure the VCC pin of the OLED is connected to 5 volts and not 12 volts.

## Battery, solar panel, and solar charge controller
The battery might last a long time, but you could use a solar panel to keep it charged. 

I used a small 18 volt/ 15 watt solar panel and a solar charge controller that can receive up to around 25 volts and charge a sealed, lead acid (AGM) battery.

The ground (black) and positive (red) wire from the solar panel will connect to the corresponding solar panel terminals on the charge controller. You will then need to  connect a ground and positive wire between the corresponding terminals on the battery and the solar charge controller. 



# Wiring  
#### Connections between components and the Arduino Pro Mini (3.3v) microcontroller

## Soil moisture sensor
| Soil sensor    |      |  Arduino Pro Mini   |
| :---:          |:---: |  :---:          |
| GND            | ---> |  GND            |
| VCC            | ---> |  9             |
| Data           | ---> |  A0             |

## Mosfet, battery, and Attiny85
I used an [IRLB8721](https://www.digikey.com/en/products/detail/infineon-technologies/IRLB8721PBF/2127670) logic-level (meaning it can be turned off/on with 3.3v or 5v microcontrollers) mosfet and a 18650 3.7 volt lithium ion battery. When fully charged, the battery will be close to 4.2 v. Ideally, one should provide 3.3 v to the Pro Mini, which is possible via a voltage regulator. I omitted the voltage regulator, however, in an effort to conserve battery power and in light of the fact that I have not had any problems doing so.

In making the connections below it is helpful to understand how pins are designated on the Attiny85 microcontroller. An Attiny85 has 8 pins as indicated [here](https://solderingmind.com/attiny85-microcontroller-working-pin-out-and-programming).

1. Connect the Gate pin of the mosfet to pin PB3 of the Attiny85. To make sure the Pro Mini stays off when it is supposed to, you can connect one leg (wire) of a 100 ohm resistor to the Gate pin of the mosfet and the other leg (wire) of the 100 ohm resistor to ground (GND) of the Attiny85. 
2. Connect the Drain pin of the mosfet to a ground (GND) pin of the Arduino Pro Mini.
3. Connect the Source pin of the mosfet to ground (GND) of the Attiny85.
4. Connect the negative (black; ground) terminal of the battery to the ground pin of the Attiny85.
5. Connect the positive (red; power) terminal of the battery to the VCC pin of the Attiny85.  

See the photo below to identify the Gate, Drain, and Source pins on the mosfet. Note that the photo identifies the pin with the black portion (with writing) of the mosfet facing you.

![MosfetLabeled](https://github.com/user-attachments/assets/84e01369-fc0b-42bd-acd3-579d18a86e7e)

## Battery and Arduino Pro Mini
####
Connect the positive terminal of the battery to the 3V3 pin of the Arduino Pro Mini. Thus, the positive side of the battery will connect to the power pins of both the Attiny85 (mentioned previously) and the Pro Mini. This works out fine with a 3.7v 18650 battery (or two of these batteries connected in parrallel--so that voltage stays the same) since it will not overpower either device. (If the device being switched on and off by the mosfet requires more power than what the Attiny85 can handle, you would need a separate power source for the device being switched on and off, and you would not connect the higher-power source to the Attiny85.)

## Arduino Pro Mini and LoRa RFM95 transceiver
####'
For a webpage displaying the pinout of the Arduino Pro Mini, click [here](https://land-boards.com/blwiki/index.php?title=Arduino_Pro_Mini).
For a webpage displaying the pinout of the LoRa RFM95 transceiver, click [here](https://www.mobilefish.com/developer/lorawan/lorawan_quickguide_build_lora_node_rfm95_arduino_uno.html)

#### LoRa transceiver
| LoRa           |       | Arduino Pro Mini  |
| :---:          | :---: | :---:             |
| GND            |  ---> | GND               |
| VCC/VIN        |  ---> | 3v3               |
| D0/GO          |  ---> | 3                 |
| SCK            |  ---> | 13                |
| MOSI           |  ---> | 11                |
| MISO           |  ---> | 12                |
| CS/NSS/SS      |  ---> | 4                 |         

Note that although pin 10 on the Pro Mini is shown as SS, SS can be assigned to other pins in Arduino IDE code. The Arduino IDE sketch (code) related to this build designates SS as pin 4. I did this, in part, to make wiring easier, to reduce the number of wires being connected to one side of the Pro Mini.

Keep ground connections between the LoRa and ProMini, separate from ground of the Attiny85. Failure to keep them separate will result in the ProMini always being powered on, even when it is supposed to be off, because it will have a connection via ground to power from the battery.



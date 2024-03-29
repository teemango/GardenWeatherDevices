# Wiring connections for connecting a transceiver (LoRa RFM95W), temperature/humidity sensor (SHT31), rain gauge (reed switch), and LED to an ATTINY85 microcontroller.


|LoRa RFM95| Attiny85 Pin# |
|----------|:---:          |
|GND       |4 (GND)        |
|3V3       |8 (VCC)        |
|NSS       |3 (PB4)        |
|SCK       |7 (PB2)        |
|MOSI      |6 (PB1-MISO)   |
|MISO      |5 (PB0- MOSI)  |

|SHT31 | Attiny85 Pin# |
|---------|:---:         |
|GND      | 4 (GND)      |
|VCC      | 8 (VCC)      |
|SCL      | 7 (PB2)      |
|SDA      | 5 (PB0)      |


|Reed Switch | Attiny85 Pin# |
|-------------|:---:         |
|One end      |4 (GND)       |
|Other end    |3 (PB4)       |

|LED          | Attiny85 Pin# |
|-------------|:---:         |
|Long leg (anode +) | 2 (PB3) in series with a 300 ohm resistor       |
|Short end (cathode -)  | 4 (GND)       |

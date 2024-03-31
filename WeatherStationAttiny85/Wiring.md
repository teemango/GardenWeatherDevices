# Wiring for a weather station with rainfall monitored by an ATTINY85 and air temperature and humidity by an ESP32.

## Wiring connections for connecting a transceiver (LoRa RFM95W) and reed switch to an ATTINY85 microcontroller 

|LoRa RFM95| Attiny85 Pin# |
|----------|:---:          |
|GND       |4 (GND)        |
|3V3       |8 (VCC)        |
|NSS       |3 (PB4)        |
|SCK       |7 (PB2)        |
|MOSI      |6 (PB1-MISO)   |
|MISO      |5 (PB0- MOSI)  |

|Reed Switch | Attiny85 Pin# |
|-------------|:---:         |
|One end      |4 (GND)       |
|Other end    |3 (PB4)       |


## Wiring connections for connecting a transceiver (LoRa RFM95W), temperature/humidity sensor (SHT31), and mini fan (5v but it still spins with 3.3 v--just slower) to a Firebeetle ESP32-E microcontroller
Firebeetle pins like GND, 3V3, SCK, MOSI, and MISO are marked on the Firebeetle itself and do not have to be designated in the sketch/code for this project. Input/Output pins like D3 and D13 are also marked on the Firebeetle board and are mentioned below in parentheses in case the added info is helpful for wiring; to designate these pins (D3, D12, D13) in the sketch, the corresponding numbers (26 for D3; 4 for D12; and 12 for D13) are used that appear in the pinout on DFROBOT web page: https://www.dfrobot.com/product-2195.html. 

|LoRa RFM95| Firebeetle Pin# |
|----------|:---:            |
|GND       |GND              |
|3V3       |3V3              |
|NSS       |26 (D3)          |
|SCK       |SCK              |
|MOSI      |MOSI             |
|MISO      |MISO             |
|DI0       |4 (D12)          |

|SHT31    | Firebeetle Pin# |
|---------|:---:         |
|GND      | GND          |
|VCC      | 3V3          |
|SCL      | SCL          |
|SDA      | SDA          |

|Fan      | Firebeetle Pin# |
|---------|:---:         |
|GND      | GND          |
|VCC      | 12 (D13)     |


----------------------------------------------------------------------------------------------------------------------------

# Below are connections for a setup that does not seem to work consistently but retained here for reference. 
They are for monitoring rain and temp/humidity with an Attiny85. Had trouble with the system freezing/data would no longer be sent/received. Another version of it involved the LED replaced by a fan.
-------------

|LoRa RFM95| Attiny85 Pin# |
|----------|:---:          |
|GND       |4 (GND)        |
|3V3       |8 (VCC)        |
|NSS       |3 (PB4)        |
|SCK       |7 (PB2)        |
|MOSI      |6 (PB1-MISO)   |
|MISO      |5 (PB0- MOSI)  |

|Reed Switch | Attiny85 Pin# |
|-------------|:---:         |
|One end      |4 (GND)       |
|Other end    |3 (PB4)       |


|SHT31 | Attiny85 Pin# |
|---------|:---:         |
|GND      | 4 (GND)      |
|VCC      | 8 (VCC)      |
|SCL      | 7 (PB2)      |
|SDA      | 5 (PB0)      |


|LED          | Attiny85 Pin# |
|-------------|:---:          |
|Long leg (anode +) | 2 (PB3) in series with a 300 ohm resistor       |
|Short end (cathode -)  | 4 (GND)       |



|LED          | Attiny85 Pin# |
|-------------|:---:         |
|Long leg (anode +) | 2 (PB3) in series with a 300 ohm resistor       |
|Short end (cathode -)  | 4 (GND)       |

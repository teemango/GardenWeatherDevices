# Connections for Weather Station Sensors

## Connections for sensors connected to the Wemos Lolin 32


|LoRa RFM95 for Lolin (Air/Hum)| Lolin Pin# |
|----------|:---:          |
|GND       |GNd        |
|3V3       |3V3        |
|NSS       |16        |
|SCK       |18        |
|MOSI      |23   |
|MISO      |19  |
|Dio0      |2  |

|SHT31D (Temp/Hum) |Lolin32 Pin # |
|----------|:---:          |
|GND       |GND        |
|VIN       |3V3        |
|SCL       |22        |
|SDA       |21        |

|Fan (for SHT31) |Lolin32 Pin # |
|----------|:---:          |
|GND       |GND        |
|VCC       |17        |

|Max 44009 (Light) |Lolin32 Pin # |
|----------|:---:          |
|GND       |GND        |
|VIN       |3V3        |
|SCL       |22        |
|SDA       |21        |

|Soil moisture sensor |Lolin32 Pin # |
|----------|:---:          |
|GND       |GND        |
|VCC       |3V3        |
|AOUT       |35        |

|DS18B20 (Soil temperature) |Lolin32 Pin # |
|----------|:---:          |
|GND       |GND        |
|Signal       |3V3 with a 4.7K resistor between pin 32 and 3V3       |
|VDD       |32        |


## Connections to the Attiny85 (for handling rain)

|LoRa RFM95 for Attin85 (Rain)| Attiny85 Pin# |
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

|LED          | Attiny85 Pin# |
|-------------|:---:         |
|Long leg (anode +) | 2 (PB3) in series with a 300 ohm resistor       |
|Short end (cathode -)  | 4 (GND)       |

Power for Attiny85: connect to 3V3 supplied by the Lolin32 (it has a voltage regulator that converts 3.7 to 4.2 v from solar-charged 3.7 v lithium batteries to 3.3v)


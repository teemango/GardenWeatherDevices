

# Connections for LoRa Gateway for Micro SD Logging

## The LoRa RFM95 (915MHZ) transceiver to the Wemos Lolin32
Note that the SS pin on the Lolin 32 is GPIO 5. Here, though, we use pin 32. Pin 5 will be reserved for the Micro SD card module. Both the LoRa transceiver and Micro SD card module interface with the Lolin32 using the SPI protocol. It can work to have two SPI modules on the same device, but each must have a different chipselect (NSS or SS) pin. 

|LoRa RFM95 | Lolin 32 GPIO Pin|
|-----------|---------|
|GND	      | GND     |
|3V3	      | 3V3     |  
|NSS (SS)   | 32      |
|SCK	      | 18      |
|MOSI	      | 23      |
|MISO	      | 19      |
|Dio0	      | 33      |
|RST	      | 25      |


|Micro SD Module | Lolin 32 GPIO Pin|
|-----------|---------|
|GND	      | GND     |
|3V3	      | 3V3     |  
|SS (CS)	  | 5      |
|SCK (CLK)  | 18      |
|MOSI	(DI)  | 23      |
|MISO	(DO)  | 19      |

|DS3231 RTC | Lolin 32 GPIO Pin|
|-----------|---------|
|GND	      | GND     |
|3V3	      | 3V3     |  
|SDA    	  | 21      |
|SCL	      | 22      |


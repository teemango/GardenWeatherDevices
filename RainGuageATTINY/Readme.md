This device measures rainfall from a tipping bucket rain gauge. It counts pulses from a reed switch and converts that data to height of rainfall.

Modification of the LoRa library (header [.h] and cpp files) are needed to interface the LoRa RFM95 transceiver with the Attiny85. This is explained below:

  The LoRa functionality is based on the Sandeepmistry library found here: https://github.com/sandeepmistry/arduino-LoRa. It requires some modification to work with the     
  ATTINY85, as explained by T Zondove (2022) here: https://www.youtube.com/watch?v=amkT5NtOgWc. Add the sandeepmistry library to your Arduino library folder, rename it as 
  "TinyLoRa," navigate to the "src" folder, and replace the ".h" and ".cpp" files with the two that are in the RainGaigeATTINY/Libraries/TinyLoRa folder in this 
  github repository. Those files reflecct all of the modifications presented by T Zondove. Make sure the files are named "TinyLoRa.cpp" and "TinyLoRa.h"; otherwise, Arduino 
  IDE will not be able to find the TinyLoRa library. (taken from: https://github.com/ECHOInternational/Microcontrollers/blob/main/Temp_Humidity_Monitor_ATTINY85/README.md)

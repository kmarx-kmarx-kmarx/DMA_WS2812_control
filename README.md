# DMA_WS2812_control
Control individually-addressable WS2812 LEDs with SPI Direct memory address, saving memory usage on dev boards.

This project is inspired by https://github.com/benheck/SPI-Neopixel ; I am using the schematic provided by Ben Heck, but the PCB design and code are all my own.

The WS2812 chips controlling the LEDs receive control signals from the microcontroller where a square pulse with period 1.15 us and 30% duty represents a 0 and a 1.3 us pulse with 53% duty represents a 1. This is typically implemented by storing "100" or "110" in memory to represent a 0 or 1 respectively and outputting the pulse train using direct memory access. This method uses three bits to store one bit of information which can lead to memory bottlenecks if one wishes to drive many LEDs. 

The PCB takes in a clock signal and a pulse train and converts the signal into timing the WS2812 can understand.

TODO: Assemble and test PCBs, write code.

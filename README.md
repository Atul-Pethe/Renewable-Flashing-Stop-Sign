# Renewable-Flashing-Stop-Sign
## TLDR
Worked in a team of 3 people to design, implement, program a board, and present to my Advanced Renewable Energy class and to my Advanced Renewabele Energy professor a stop sign that utilizes solar power to flash LEDs around its edges. Also presented to Cluster 6 (Introduction to Smart and Sustainable Power) at UCSC Cosmos.

## Purpose
Traditional traffic control devices, while essential, are often inadequate in low-visibility environments. At the UCSC campus, frequent fog creates a safety gap that static signage cannot bridge. By implementing active LED-enhanced signals—similar to those used in school zones—visibility and driver compliance can be significantly improved under adverse conditions.

## My Main Parts
- DC-DC Boost Converter: Provides steady voltage output to microcontroller (Nucleo F303K8)
- Nucleo F303K8: Used to handle flashing lights logic
- Charging PCB: Used to handle charging the battery to allow for easy

## My Main Tools
My main tools that I used was Arduino for handling the flashing lights logic in the Stop Sign, as well as a multimeter to test certain points of the circuit to ensure that the components are working properly. 


## Engineering Process
### The Initial Challenge
The original design utilized a Light Dependent Resistor (LDR) to autonomously regulate the brightness of the perimeter LEDs. However, testing revealed a fundamental logic flaw: the LDR’s resistance increases as ambient light decreases. In a direct series configuration, this caused the LEDs to dim or turn off at night—the exact opposite of the intended behavior.

### The Solution: Microcontroller Integration
Rather than attempting to balance a complex analog inverter circuit, I pivoted to a more robust, digital approach. I integrated a microcontroller to interface with the sensors within the Photovoltaic (PV) cell.

By using the PV cell’s voltage as a light-level signal, I programmed the microcontroller to:
- Monitor ambient light levels via the PV input.
- Execute logic to trigger the LEDs only when the light fell below a specific threshold.
- Regulate current to the LEDs for consistent brightness.

This shift to a microcontroller-based architecture successfully resolved the logic issue and provided much greater control over the system's power efficiency.

## Design
![alt text](https://github.com/Atul-Pethe/Power-Distribution-Board/blob/main/Power%20Distribution%20Board%20Schematic.png?raw=true)

## Overall Result
The result of this board was that my group was invited to present this project at the COSMOS Cluster 6 - Introduction to Smart and Sustainable Power

## Problems that I Faced
The problem that I faced was that instead of using a power-hungry microcontroller, I could have used a fully hardware system taht would have saved overall power, and been slightly more accurate.

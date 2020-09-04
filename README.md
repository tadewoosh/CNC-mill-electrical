# CNC mill: electrical
The electrical part of the CNC mill project.

This repo contains the files needed for construction of a custom machine controller based on the [GRBL 1.1](https://github.com/gnea/grbl) project. If you dont want to make your own PCB you can still use GRBL compatible Arduino boards.

## Block diagram
![diagram1](./Images/diagram1.png)

## Main controller
<img align="right" height="200" src="./Images/pcb.PNG">

The main controller board is an AVR ATMega8 based device aiming to replace the Arduino board as the motion controller. The reason why one might want to use this board instead of Arduino is that it provides:
* Galvanic insulation of the machine and the PC
* Robust power circuitry
* Robust connectors suitable for more "industrial" use
* Additional noise-reducing and LPF circuitry for the inputs and outputs
* A high-voltage output for the coolant output


## Motor Drivers
<img align="right" height="200" src="./Images/driver1.PNG">
The 2DM556S 4.2 RMS drivers are used.

The current limiter on the driver is set to 3,5A in order to drive the 60HS100-3504A08-D24 4,3N.m stepper motors.

The microstepping is set to 2000.


## Spindle Inverter

## Inputs

## Outputs

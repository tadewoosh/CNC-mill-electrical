# CNC mill: electrical
The electrical part of the CNC mill project.

This repo contains the files needed for construction of a custom machine controller based on the [GRBL 1.1](https://github.com/gnea/grbl) project. If you dont want to make your own PCB you can still use GRBL compatible Arduino boards.

## Block diagram
![diagram1](./Images/diagram1.png)

## Motion controller
<img align="right" height="200" src="./Images/pcb.PNG">

### Why not Arduino?
The main controller board is an AVR ATMega8 based device aiming to replace the Arduino board as the motion controller. The reason why one might want to use this board instead of Arduino is that it provides:
* Galvanic insulation of the machine and the PC
* Robust power circuitry
* Robust connectors suitable for more "industrial" use
* Additional noise-reducing and LPF circuitry for the inputs and outputs
* A high-voltage output for the coolant output

The Eagle project files are hosted in this repository along with the CAM configuration and its output (GERBER, drillfiles etc.) allowing for the easy PCB manufacturing/ordering.

In order to program a blank AVR chip with GRBL one needs first to obtain the Arduino bootloader allowing to update the frmware via the serial port.

### Detailed specification

<img align="right" height="200" src="./Images/schematic1.png">
<img align="right" height="200" src="./Images/schematic2.png">

* up to 36V DC supply voltage when using **TSR 1-2450**, otherwise **7805** specification applies.
* reverse power supply protection
* reset switch
* ISP connector (*NOTE: The programming using ISP shlud not be used when the spindle inverter is ON*)
* debug serial commincation port with 5V tap
* USB to serial converter based on FTDI with optoisolation
* 3 sets of STEP/DIR/ENABLE connectors for stepper drivers with LED indicators
* User switches inputs (active low, with debouncing circuitry): ABORT, HOLD, START
* Probe input with debouncing circuitry and LED indication
* 3 limit switches inputs, active low, with debouncing circuitry and LED indication
* High voltage (supply), high current (1A) output for driving the cooland relay with Shottky protection
* PWM or analog (using LPF) 0-5V output for spindle speed and direction control with LED indication

## Motor Drivers
<img align="right" height="200" src="./Images/driver1.PNG">

The **2DM556S** 4.2 RMS drivers are used.

The current limiter on the driver is set to 3,5A in order to drive the 60HS100-3504A08-D24 4,3N.m stepper motors.

The microstepping is set to 2000.

## Spindle Inverter
<img align="right" height="200" src="./Images/inverter2k2.jpg">

A chineese set of inverter and spindle is used. The rated power of both is 2.2kW.

The inverter model is **YL620-A-2.2kW**. It is powered by a single-phase 230V mains.

## Connecting Inputs

## Connecting Outputs

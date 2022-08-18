# Micro-Lab-4-Group-4-
Water level controlling system of a water tank

## Introduction 
<b> Pic Microcontroller </b>
align="justify"
The PIC microcontroller is controlled by software and programmed in such a way that it performs different tasks and controls a generation line. PIC microcontrollers are used in different new applications such as smartphones, audio accessories, and advanced medical devices.
The PIC microcontroller PIC16f877A is one of the most renowned microcontrollers in the industry. The PIC16F877A microcontroller is very convenient to use, the coding or programming of this controller is also easier. One of the main advantages is that it can be write-erase as many times as possible because it uses FLASH memory technology. It has a total number of 40 pins and there are 33 pins for input and output. PIC16f877A finds its applications in a huge number of devices. It is used in remote sensors, security and safety devices, home automation and many industrial instruments. The cost of this controller is low and its handling is also easy. It is flexible and can be used in areas where microcontrollers have never been used before as in microprocessor applications and timer functions etc.

<b> Pickit Programmer Debugger </b>

The PICkit 3 programmer/debugger is a simple, low-cost in-circuit debugger that is controlled by a PC running MPLAB IDE software on a Windows platform. The PICkit 3 debugger is an integral part of the development engineer’s toolsuite. The application usage can vary from software development to hardware integration.

The PICkit 3 debugger is a debugger system used for hardware and software development of Microchip PIC microcontrollers and PIC Digital Signal Controllers that are based on In-Circuit Serial Programming and Enhanced In-Circuit Serial Programming 2-wire serial interfaces. In addition to debugger functions, the PICkit 3 debugger system also may be used as a development programmer.




## Objectives
•	To develop a small water level controlling system of a water tank using the knowledge of interrupts.

<ul>
<li> PCB design
<li> PIC16F877A microcontroller	
<li> Breadboard 
<li> 3 x IR obstacle sensors   
<li> 2 x 3V DC motors 
<li> Resistors (330Ω, 10kΩ)
<li> Jumper wires (Male-Male, Male-Female)
<li> Capacitors (22pF)
<li> Crystal oscillator (20MHz)	
<li> Female headers
<li> 5V relays
<li> Pickit 3 programmer
<li> Breadboard Supply module 

</ul>

## Methodology
<b> Designing the Code </b> <br> </br>
// PIC16LF877A Configuration Bit Settings <br> </br>
// 'C' source line config statements <br> </br>
// CONFIG <br> </br>
#pragma config FOSC = HS        // Oscillator Selection bits (HS oscillator) <br> </br>
#pragma config WDTE = OFF       // Watchdog Timer Enable bit (WDT disabled) <br> </br>
#pragma config PWRTE = OFF      // Power-up Timer Enable bit (PWRT disabled) <br> </br>
#pragma config BOREN = OFF      // Brown-out Reset Enable bit (BOR disabled) <br> </br>
#pragma config LVP = OFF        // In-Circuit Serial Programming Enable bit <br> </br>
#pragma config CPD = OFF        // Data EEPROM Memory Code Protection bit <br> </br>
#pragma config WRT = OFF        // Flash Program Memory Write Enable bits <br> </br>
#pragma config CP = OFF         // Flash Program Memory Code Protection bit <br> </br>

// #pragma config statements should precede project file includes. <br> </br>
// Use project enums instead of #define for ON and OFF. <br> </br>

<p> Initially, the oscillator selection bits were configured to high-speed oscillator (HS). All the other configurations bits were set to OFF setting and thus the configuration bits were generated for the code. </p>


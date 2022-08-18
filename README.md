# Micro-Lab-4-Group-4-
Water level controlling system of a water tank

## Introduction 
<b> Pic Microcontroller </b>

The PIC microcontroller is controlled by software and programmed in such a way that it performs different tasks and controls a generation line. PIC microcontrollers are used in different new applications such as smartphones, audio accessories, and advanced medical devices.
The PIC microcontroller PIC16f877A is one of the most renowned microcontrollers in the industry. The PIC16F877A microcontroller is very convenient to use, the coding or programming of this controller is also easier. One of the main advantages is that it can be write-erase as many times as possible because it uses FLASH memory technology. It has a total number of 40 pins and there are 33 pins for input and output. PIC16f877A finds its applications in a huge number of devices. It is used in remote sensors, security and safety devices, home automation and many industrial instruments. The cost of this controller is low and its handling is also easy. It is flexible and can be used in areas where microcontrollers have never been used before as in microprocessor applications and timer functions etc.

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
<p>
</p>

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

// #pragma config statements should precede project file includes.
// Use project enums instead of #define for ON and OFF.


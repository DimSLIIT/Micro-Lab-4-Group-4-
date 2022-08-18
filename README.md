# Micro-Lab-4-Group-4-
Water level controlling system of a water tank

<p>

</p>

## Introduction 

<p>

</p>

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
<b> Designing the Code </b>
// PIC16LF877A Configuration Bit Settings

// 'C' source line config statements

// CONFIG
#pragma config FOSC = HS        // Oscillator Selection bits (HS oscillator)
#pragma config WDTE = OFF       // Watchdog Timer Enable bit (WDT disabled)
#pragma config PWRTE = OFF      // Power-up Timer Enable bit (PWRT disabled)
#pragma config BOREN = OFF      // Brown-out Reset Enable bit (BOR disabled)
#pragma config LVP = OFF        // In-Circuit Serial Programming Enable bit 
#pragma config CPD = OFF        // Data EEPROM Memory Code Protection bit 
#pragma config WRT = OFF        // Flash Program Memory Write Enable bits 
#pragma config CP = OFF         // Flash Program Memory Code Protection bit 

// #pragma config statements should precede project file includes.
// Use project enums instead of #define for ON and OFF.


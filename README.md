# Micro-Lab-4-Group-4-
Water level controlling system of a water tank

## Introduction 
<b> Pic Microcontroller </b> <br> </br>
<p align="justify">
The PIC microcontroller is controlled by software and programmed in such a way that it performs different tasks and controls a generation line. PIC microcontrollers are used in different new applications such as smartphones, audio accessories, and advanced medical devices.
The PIC microcontroller PIC16f877A is one of the most renowned microcontrollers in the industry. The PIC16F877A microcontroller is very convenient to use, the coding or programming of this controller is also easier. One of the main advantages is that it can be write-erase as many times as possible because it uses FLASH memory technology. It has a total number of 40 pins and there are 33 pins for input and output. PIC16f877A finds its applications in a huge number of devices. It is used in remote sensors, security and safety devices, home automation and many industrial instruments. The cost of this controller is low and its handling is also easy. It is flexible and can be used in areas where microcontrollers have never been used before as in microprocessor applications and timer functions etc.

<b> Pickit Programmer Debugger </b> <br> </br>
<p align="justify">
The PICkit 3 programmer/debugger is a simple, low-cost in-circuit debugger that is controlled by a PC running MPLAB IDE software on a Windows platform. The PICkit 3 debugger is an integral part of the development engineer’s toolsuite. The application usage can vary from software development to hardware integration. The PICkit 3 debugger is a debugger system used for hardware and software development of Microchip PIC microcontrollers and PIC Digital Signal Controllers that are based on In-Circuit Serial Programming and Enhanced In-Circuit Serial Programming 2-wire serial interfaces. In addition to debugger functions, the PICkit 3 debugger system also may be used as a development programmer.

<b> Sensor </b> <br> </br>
<p align="justify">
A sensor is a device that produces an output signal for the purpose of sensing a physical phenomenon. There are so many types of sensors which used in the industry. IR sensors, motion detect sensors, pressure sensors, temperature sensors are some of them. The basic concept of an Infrared Sensor which is used as Obstacle detector is to transmit an infrared signal, this infrared signal bounces from the surface of an object and the signal is received at the infrared receiver.


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
#include <xc.h> //Header file for PIC device <br> </br>
#define _XTAL_FREQ 20000000  //Oscillator frequency of 20MHz <br> </br>

<p> Initially, the oscillator selection bits were configured to high-speed oscillator (HS). All the other configurations bits were set to OFF setting and thus the configuration bits were generated for the code. </p>

<b> Main function <b> <br> </br>
  void main(void){ //main method <br> </br>
    
    GIE = 1;    //Global Enable Interrupt Bit in INTCON register 
    INTE = 1;   //External Interrupt Enable Bit in INTCON register
    INTF = 0;   //Interrupt Enable Flag Bit in INTCON register
    INTEDG = 1; //Interrupt Edge Select Bit in OPTION register
    
    TRISC0 = 0; //Configuring RC0 pin as an output for Motor 1
    TRISC1 = 0; //Configuring RC1 pin as an output for Motor 2
    
    TRISB2 = 1; //Configuring RB2 pin as an input for Sensor 01
    TRISB1 = 1; //Configuring RB1 pin as an input for Sensor 02
    TRISB0 = 1; //Configuring RB0 pin as an input for Sensor 03 (Interrupt pin)
    
<img src="https://user-images.githubusercontent.com/111265007/185430125-0e73a177-ee9e-4a20-b6a1-a57473c36729.png" width = "800" height = "550"/>
<p> 
<p align="justify"> 
The PIC16F87X family has up to 14 sources of interrupt. The interrupt control register (INTCON) records individual interrupt requests in flag bits. It also has  individual and global interrupt enable bits. A global interrupt enable bit, GIE (INTCON) enables (if set) all unmasked interrupts or disables (if cleared) all interrupts. When bit GIE is enabled, and an interrupt’s flag bit and mask bit are set, the interrupt will vector immediately. Individual interrupts can be disabled through their corresponding enable bits in various registers. Individual interrupt bits are set, regardless of the status of the GIE bit. The GIE bit is cleared on RESET. <br> </br> 
<p align="justify">
External interrupt on the RB0/INT pin is edge triggered, either rising, if bit INTEDG in OPTION_REG is set, or falling, if the INTEDG bit is clear. When a valid edge appears on the RB0/INT pin, flag bit INTF (INTCON) is set. This interrupt can be disabled by clearing enable bit INTE (INTCON). Flag bit INTF must be cleared in software in the Interrupt Service Routine before re-enabling this interrupt.
1st pin and 2nd pin or pin 0 and pin 1 of PORTC was configured to be output pins by the function of TRISC register. These pins were used for the 2 DC motors. 
Also, 3 pins (pin 0 (Interrupt pin), pin 1, pin 2) from the PORTB were configured as input pins using TRISB register. These pins were used for getting the sensor outputs to the microcontroller. </p> 

<b> While loop </b>
 while(1){ 
        
        if(RB0 == 0 && RB1 == 0 && RB2 == 1){ //Checking sensor 1, 2, 3
            RC0 = 1; //Motor 1 ON
            RC1 = 0; //Motor 2 OFF
        }
        if(RB0 == 0 && RB1 == 1 && RB2 == 1){ //Checking sensor 1, 2, 3
            RC0 = 1; //Motor 1 ON
            RC1 = 0; //Motor 2 OFF
        }
        if(RB0 == 0 && RB1 == 0 && RB2 == 0){ //Checking sensor 1, 2, 3
            RC0 = 0; //Motor 1 OFF
            RC1 = 0; //Motor 2 OFF
        }
    }
    return;
    }
<img src = "https://user-images.githubusercontent.com/111265007/185431051-1c3055e5-b1cd-48f8-9ed0-9b73dc3cdff9.png" width = "800" height = "200"/>
<p>
<p align="justify">
Three cases were examined. First the 3 sensors were checked for the 1st condition where the Sensor 1 is ON while the other two sensors are OFF. This means when the RB2 pin (Sensor 1) gives a logic high input, the RC0 pin (Motor 1) should give a logic high as well. By this the Motor 1 was set to ON state while the Motor 2 is off. 
Next in case 2, Sensor 1 and 2 were set to give a logic low input to the PIC IC while the Sensor 3 gives a logic high output which results the Motor 1 to stay in ON state and Motor 2 to be in OFF state as in case 1. No change in output was occurred. 
Finally when sensor 3 gives a logic high, the interrupt routine was triggered and hence the Motor 2 was set ON for a small period of time (initiating a delay) where the Motor 1 will cease of its operation. Here the interrupt routine will run and the operation follows the instructions as given in the interrupt routine.
Another external case was inspected where when all the sensors are at logic low, both the motors were ceased of its operation. </p>


<b> Interrupt Routine </b>



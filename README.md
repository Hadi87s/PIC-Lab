# PIC32 Timer and Interrupt Experiment

## Overview
This repository contains the implementation of Experiment 6 focused on Timers and Interrupts using the PIC32 microcontroller on the ChipKIT Pro MX7 processor board. The experiment demonstrates how to use PICTM32 timers to implement a synchronized multi-rate periodic control system by polling the timer interrupt flag, as well as how to detect events using interrupts.

## Objectives
- Understand the operation of PIC32 timers
- Implement a synchronized multi-rate periodic control system
- Explore event detection using interrupts
- Utilize Change Notice (CN) interrupts for button inputs

## Hardware Requirements
- ChipKIT Pro MX7 processor board with USB cable
- Microchip MPLAB X IDE
- MPLAB XC32++ Compiler

## Implementation Details

### Timer Configuration
The implementation uses the MPLAB Harmony Timer Driver library to interface with the PIC32 Timer peripherals. Specifically, the Static Timer Driver is configured to:
- Use Timer Module ID: TMR_ID_2
- Operation Mode: DRV_TMR_OPERATION_MODE_32_BIT
- Generate interrupts at a 1ms interval
- Set interrupt priority level 2 and subpriority level 0

### Change Notice (CN) Interrupts
The system utilizes CN interrupts to detect button presses:
- CN8 (BTN1 - RG6) and CN9 (BTN2 - RG7) are enabled
- CN interrupt priority is set to level 1 and subpriority level 0
- Internal pull-up resistors are disabled (using external pull-ups on the board)

### Functionality
The system operates entirely using foreground processes:
1. **BTN1 Mode**: When BTN1 is pressed, the LED displays a binary counter from 0 to 15 and repeats
2. **BTN2 Mode**: When BTN2 is pressed, the LED flashes on and off at regular intervals

### Implementation Notes
- The Timer ISR runs at 1ms intervals and is used to create delay functions
- The CN interrupt detects both press and release events on the buttons
- A debouncing mechanism is implemented to prevent false triggers
- The main application state machine handles the LED behaviors based on button inputs

## File Structure
- `app.c` - Contains the main application state machine
- `app.h` - Header file for the application
- `system_interrupt.c` - Contains ISR handlers for Timer and CN interrupts
- `system_init.c` - Contains initialization code for peripherals

## Setup Instructions
1. Clone this repository
2. Open the project in MPLAB X IDE
3. Configure the project properties to use the XC32++ Compiler
4. Build the project and program the ChipKIT Pro MX7 board
5. Test the functionality using BTN1 and BTN2

## Notes on PIC32 Timers
PIC32 timers have period registers (PR1, PR2, etc.) used to set maximum count values. When the time count reaches the value stored in the period register, a timer interrupt flag is set and the timer register resets to zero. The timer interrupt flag remains set until cleared by software.

# Experiment 2: Input and Output (IO) - PIC32

## Overview

This experiment focuses on **digital Input/Output (IO) operations** using the **PIC32 microcontroller**. You will configure **digital IO ports** to control output devices (LEDs) and read input signals (push buttons).

## Objectives

- Understand **IO port configuration** on the PIC32.
- Learn to control **LEDs** using digital outputs.
- Read input from **push buttons** and process user interaction.
- Implement simple **polling-based IO control**.

## Equipment Required

- **PIC32 Development Board**
- **MPLAB X IDE**
- **XC32 Compiler**
- **PICkit 3 (or similar) Programmer**
- **LEDs, Push Buttons, Resistors**

## Theory

- The **PIC32 IO ports** can be configured as **input** or **output** using the following registers:
  - `TRISx`: Sets the pin direction (**1 = Input**, **0 = Output**).
  - `LATx`: Writes output values to pins.
  - `PORTx`: Reads input values from pins.


# 🔢 Experiment 6: Keypad Handling - PIC Lab

This repository contains the implementation of **Keypad Handling** using the chipKIT™ Pro MX7 and PmodKYPD module as part of the PIC microcontroller lab experiments.

## 🎯 Objectives

- Interface a 16-button alphanumeric keypad with the PIC32-based chipKIT™ Pro MX7 board.
- Detect and display the pressed key via:
  - UART on a serial terminal (HyperTerminal).
  - Binary output on the board's onboard LEDs.

## 🧰 Equipment Used

- chipKIT™ Pro MX7 processor board
- PmodKYPD (16-Button Keypad)
- USB cable
- MPLAB® X IDE
- MPLAB® XC32++ Compiler
- HyperTerminal or any PC-based terminal emulator

## 🧠 Overview

The **PmodKYPD** is a matrix keypad with 4 rows and 4 columns, offering 16 input buttons. Each button press can be identified by scanning column-wise and reading row signals.

### PmodKYPD Pin Mapping

| Pin | Signal | Description     |
|-----|--------|-----------------|
| 1   | COL4   | Column 4        |
| 2   | COL3   | Column 3        |
| 3   | COL2   | Column 2        |
| 4   | COL1   | Column 1        |
| 5   | GND    | Ground          |
| 6   | VCC    | Power (3.3V)    |
| 7   | ROW4   | Row 4           |
| 8   | ROW3   | Row 3           |
| 9   | ROW2   | Row 2           |
| 10  | ROW1   | Row 1           |
| 11  | GND    | Ground          |
| 12  | VCC    | Power (3.3V)    |

## ⚙️ Implementation Steps

1. Connect the **PmodKYPD** to **Pmod Connector JA4** on the MX7 board.
2. Create a new Harmony project in MPLAB X IDE.
3. Configure:
   - **Column pins** as digital outputs.
   - **Row pins** as digital inputs.
4. Write C code to:
   - Continuously scan the keypad.
   - Identify which key is pressed.
   - Send the key value to the serial terminal.
   - Display the binary representation of the key on the 4 onboard LEDs.

💡 **Example:** If key `9` is pressed, the binary `1001` will be shown on the LEDs (LED1 and LED4 ON).

## 🖥️ Output

- Keypresses are shown in real time on the terminal emulator.
- LEDs give a visual binary representation of each key pressed.

## 🛠 Notes

- Ensure the pin mappings between Pmod and MCU are correct using the MX7 board schematic.
- Any Pmod connector can be used, but adjustments in the pin configuration will be required accordingly.


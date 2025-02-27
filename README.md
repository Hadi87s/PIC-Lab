# Bluetooth Interface (EXP4) - Microcontroller & PmodBT2

## Overview  
This experiment focuses on interfacing a **PmodBT2 Bluetooth module** with the **ChipKIT™ Pro MX7 microcontroller** to establish wireless communication between a **mobile device** and a **PC-based terminal (HyperTerminal)**. The objective is to implement a **bidirectional chat system** using **UART communication**.  

## Equipment Used  
- **ChipKIT™ Pro MX7 processor board** (with USB cable)  
- **PmodBT2 - Bluetooth Interface**  
- **Microchip MPLAB® X IDE**  
- **MPLAB® XC32++ Compiler**  
- **PC-based terminal emulation software (HyperTerminal®)**  
- **Mobile device with BlueTerm app**  

## Key Concepts  
- **UART-based Bluetooth communication**  
- **Data & Command modes of the PmodBT2**  
- **Configuring UART communication in MPLAB Harmony**  
- **Interfacing a Bluetooth module with a microcontroller**  

---

## Implementation Steps  

### 1. Setup and Initial Communication  
1. **Connect the PmodBT2 module** to the **UART2 (JF) header** on the ChipKIT™ Pro MX7 board.  
2. **Connect the ChipKIT™ Pro MX7 to a PC** via a USB cable.  
3. **Install the BlueTerm app** on a mobile device.  
4. **Pair the Bluetooth module** with the mobile:  
   - Open the **BlueTerm app**, click **"Connect device"**, and select **RNBT - 61E5**.  
5. **Enter Command Mode:**  
   - Send **"$$$"** from the mobile app. The module should respond with **"CMD"**.  
6. **Try basic Bluetooth commands** (e.g., `D`, `GB`, `GR`) to explore module capabilities.  

### 2. Sending Data via Bluetooth  
1. **Create a new MPLAB Harmony project**.  
2. **Write a simple program to send your full name** from the microcontroller to the Bluetooth interface:  
   - Configure UART2 for Bluetooth at **115.2 kbps**, **8 data bits**, **no parity**, **1 stop bit**.  
   - Send your name as a string over the Bluetooth connection.  

### 3. Implementing a Chat System  
1. **Modify the code to establish two-way communication** between:  
   - **The mobile device (via Bluetooth)**  
   - **The PC-based terminal (via UART to the microcontroller)**  
2. **Configure two separate UART instances**:  
   - **Mobile (Bluetooth UART2):** `115.2 kbps, 8N1`  
   - **PC (HyperTerminal UART1):** `57.6 kbps, 8N1`  
3. **Enable bidirectional data flow**:  
   - Messages from the **mobile device** should be relayed to **HyperTerminal on the PC**.  
   - Messages from **HyperTerminal** should be sent to the **mobile via Bluetooth**.  

---
## UART Configuration:
![UART Configuration](https://github.com/Hadi87s/PIC-Lab/blob/Exp4/firmware/Exp4.PNG)

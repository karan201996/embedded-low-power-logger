# Embedded Low-Power Data Logger  

## Overview  
This project implements a battery‑powered sensor logger optimized for ultra‑low‑power operation. The device periodically samples sensor data, timestamps it, writes it to non‑volatile storage, and enters deep sleep. It includes a simple Python script to parse and visualise the logged data.  

## Hardware Requirements  
- Low‑power MCU (e.g., STM32L4, STM32L0, or MSP430).  
- Environmental sensor (temperature, humidity, etc.).  
- Real‑time clock (RTC) with low drift.  
- SD card or external flash storage.  
- Li‑ion battery and power management circuitry.  

## Software Requirements  
- Drivers for RTC, sensor, and storage (provided in this repo).  
- A Makefile or CMake build system.  
- Python with matplotlib for data plotting.  

## Build & Run Instructions  
1. Clone this repo and set up your MCU’s toolchain.  
2. Edit `config.h` to set the sampling interval and sensor parameters.  
3. Build the firmware (`make` or `cmake --build .`) and flash it onto your board.  
4. Power the device with a battery and insert an SD card.  
5. After logging, remove the SD card and run the provided Python script to parse and plot the CSV data.  

## Features  
- Deep sleep between samples to minimise power draw.  
- Configurable logging interval and sensor settings.  
- Timestamped data storage in CSV format.  
- Includes energy consumption and battery‑life calculation examples.  

## Demo  
Deploy the logger in an environment for several hours or days. Use the Python script to produce a time‑series plot of the recorded data and evaluate battery life based on sampling frequency.  

## Future Work  
- Implement low‑battery detection and visual/notification alerts.  
- Add wireless offloading via BLE or LoRaWAN.  
- Expand to support multiple sensors and dynamic configuration. 

# ESP32 IoT Sensor Board

A custom PCB design based on this udemy project: https://www.udemy.com/course/advanced-pcb-design-with-kicad/

## Overview

This project is an advanced IoT embedded system built around the ESP32-C3 microcontroller. The board is designed for versatile sensor-based IoT applications with a focus on power efficiency, connectivity, and expandability.

## Hardware Specifications

- **Microcontroller**: ESP32-C3-WROOM-02-H4
- **Power Management**:
  - USB Type-C power input
  - LiPo battery support with integrated charging circuit (MCP73871)
  - 3.3V voltage regulation (LM1117MPX-3.3)
  - Power status LEDs
- **Connectivity**:
  - USB-C connector (SS-52400-002) for data and power
  - Wi-Fi and Bluetooth (via ESP32-C3)
- **Sensors**:
  - BME280 environment sensor (temperature, humidity, pressure)
  - MAX4466 microphone module
  - TEMT6000 ambient light sensor
- **I/O**:
  - Multiple GPIO pins
  - SPI, I2C, and UART interfaces
  - User buttons
  - Status LEDs

## Features

- **Power Management**:

  - Automatic switching between USB and battery power
  - Built-in LiPo battery charging with charge status indication
  - Low power modes for extended battery life
  - Over-current protection (0ZCH0110AF2E fuse)

- **Compact Design**:

  - Optimized PCB layout for small form factor
  - SMD components for reduced size

- **Expandability**:
  - Accessible I2C and SPI buses for additional sensors
  - Exposed GPIO pins for custom additions

## Getting Started

### Prerequisites

- Arduino IDE or PlatformIO
- USB-C cable
- 3.7V LiPo battery (optional)

### Hardware Setup

1. Connect the board to your computer using a USB-C cable
2. If using battery power, connect a compatible LiPo battery to the JST connector (observe polarity!)
3. The power status LEDs will indicate:
   - Red: Charging
   - Green: Fully charged
   - Blue: System powered on

### Software Setup

1. Install ESP32 board support in your development environment
2. Select "ESP32-C3" as the board type
3. Use the USB-CDC driver for programming and debugging

## Pin Mapping

| ESP32 Pin | Function               |
| --------- | ---------------------- |
| GPIO0     | Boot mode selection    |
| GPIO1     | TX                     |
| GPIO2     | RX                     |
| GPIO3     | SDA (I2C)              |
| GPIO4     | SCL (I2C)              |
| GPIO5     | User button            |
| GPIO6-7   | Reserved for SPI flash |
| GPIO8-9   | User LEDs              |
| GPIO10    | Ambient light sensor   |
| GPIO18    | Microphone input       |
| GPIO19-21 | Available GPIO         |

## Repository Structure

```
Advanced_PCB/
├── Advanced_PCB.kicad_pcb    - PCB layout file
├── Advanced_PCB.kicad_sch    - Schematic file
├── README.md                 - Project documentation
├── Advanced_PCB-backups/     - Backup files
└── Libraries/                - Custom component libraries
    ├── Footprints/          - PCB footprints
    └── Symbols/             - Schematic symbols
```

## License

This project is open-source hardware.

## Acknowledgments

- The original design was inspired by concepts from the Udemy course on advanced PCB design.

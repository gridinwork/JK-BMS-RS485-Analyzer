# JK BMS RS-485 Analyzer & Diagnostic Tool

Engineering software for direct communication, protocol analysis, diagnostics and testing of a **single JK BMS** over RS-485.

This project was developed as part of the **Axentum autonomous mobile robot project** during the development and commissioning of its high-power LiFePO4 traction battery system.

Unlike the later multi-BMS Battery Monitor System, this application works with **one BMS at a time** and was created primarily for protocol research, low-level diagnostics, communication testing and engineering verification.

## Project Purpose

The JK BMS RS-485 Analyzer was developed to provide direct access to the communication channel between a PC and a JK Smart Active Balance BMS.

It allows an engineer to inspect raw RS-485 traffic, send custom commands, verify Modbus communication, log packets, test communication settings and diagnose the behavior of the BMS during development.

This software was used as an engineering tool before and during development of the later Axentum multi-BMS monitoring system.

## Main Features

- Direct communication with one JK BMS over RS-485
- COM-port selection
- Configurable baud rate
- Raw HEX packet monitoring
- Timestamped received data
- Manual transmission of custom HEX commands
- Modbus command testing
- Automatic Modbus CRC16 calculation
- Quick Modbus register requests
- Communication diagnostics
- Packet logging
- CSV logging
- Manual engineering notes / event markers
- Protocol analysis
- BMS response verification
- Engineering and commissioning use

## Communication Options

### USB-RS485

Direct PC connection through a USB-to-RS485 adapter.

PC -> USB -> USB-RS485 Adapter -> RS-485 -> JK BMS

### Arduino Mega + MAX485 Bridge

The software can also be used with an Arduino Mega and MAX485 communication bridge for hardware-level protocol testing and integration work.

PC -> USB Serial -> Arduino Mega -> MAX485 -> RS-485 -> JK BMS

## Axentum Project Context

The analyzer was developed for the **Axentum project**, a large autonomous wheeled robot designed for automated handling and deployment of solar panels.

Axentum uses a custom high-power LiFePO4 traction battery architecture. During development, it was necessary to:

- select and configure the JK BMS hardware
- test RS-485 communication
- verify BMS responses
- analyze raw protocol data
- validate commands
- debug communication reliability
- confirm register values
- prepare the communication architecture for integration into the complete robot

This analyzer was one of the engineering tools used for that work.

## Relationship to the Multi-BMS Monitor

This repository represents the **single-BMS engineering and protocol-analysis tool**.

A later application was developed for the actual Axentum traction-battery architecture, where **three JK BMS units are monitored simultaneously** as one combined battery system.

Single-BMS tool:

JK BMS -> RS-485 -> JK BMS RS-485 Analyzer

Later Axentum multi-BMS system:

JK BMS #1 / #2 / #3 -> RS-485 -> Axentum 3-BMS Battery Monitor

The two applications therefore serve different purposes:

- **JK BMS RS-485 Analyzer** — low-level testing, protocol analysis, diagnostics and single-BMS communication
- **Axentum 3-BMS Battery Monitor System** — real-time monitoring and diagnostics of three BMS-controlled battery modules operating together

## Typical Engineering Workflow

1. Connect one JK BMS through USB-RS485 or the Arduino bridge.
2. Select the COM port and baud rate.
3. Establish communication.
4. Observe incoming raw packets.
5. Send test commands or Modbus requests.
6. Verify CRC and response structure.
7. Record communication logs.
8. Compare values with expected battery parameters.
9. Diagnose communication or configuration issues.
10. Use verified protocol behavior in the higher-level monitoring system.

## Software Structure

The project includes Python desktop software and support for hardware communication testing.

Main software functions include serial communication, raw-packet monitoring, Modbus request generation, CRC processing, data logging and engineering diagnostics.

The project also includes support firmware for an **Arduino Mega + MAX485 RS-485 bridge** used during hardware-level testing.

## Hardware

Primary target family: **JK Smart Active Balance BMS**

Typical interfaces used during development:

- RS-485
- USB-RS485 adapters
- Arduino Mega
- MAX485 transceiver

## Why This Tool Was Developed

During development of high-power mobile-robot battery systems, vendor PC software is often insufficient for integration and debugging. This tool was created to provide direct engineering access to the RS-485 channel and make it possible to independently inspect BMS communication, test commands, verify protocol behavior, log data, investigate communication problems and prepare reliable integration with custom robot electronics and software.

## Project Role

The work included BMS communication research, RS-485 protocol testing, communication architecture development, Modbus request testing, raw-packet analysis, diagnostics, software development, hardware bridge testing and integration with the Axentum battery-development workflow.

## Project Status

This repository documents the first engineering version used for single-BMS diagnostics and protocol analysis. It was later followed by a dedicated **three-BMS monitoring application** for the complete Axentum traction-battery system.

## Developer

**Oleg Gridin, BEng**  
CEO / Lead Engineer — GEC Engineering

Website: https://gec-engineering.tech/  
YouTube: https://www.youtube.com/@GEC_Company  
GitHub: https://github.com/gridinwork

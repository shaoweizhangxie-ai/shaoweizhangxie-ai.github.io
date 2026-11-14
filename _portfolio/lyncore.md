---
title: "LynCore: RISC-V CPU and YOLO Integration"
excerpt: "A five-stage RISC-V processor and FPGA vision system with YOLO integration."
collection: portfolio
permalink: /portfolio/lyncore/
---

## Overview

LynCore is a 32-bit RISC-V processor and system-on-chip project developed for FPGA implementation. The work spans processor architecture, bare-metal software, accelerator control and integration with a YOLO-based vision system.

## Processor and System

- Five-stage, in-order pipeline implementing RV32I, with optional RV32M integer multiplication and division.
- Machine-mode exceptions and interrupts, UART, GPIO and timer peripherals.
- Optional two-way set-associative instruction and data caches and dynamic branch prediction.
- Bare-metal C startup and application support.

## Accelerator Integration

An AXI4-Lite control bridge, task configuration registers and C driver provide a basis for issuing accelerator jobs and polling their status. Earlier control-path tests used a simulated execution model; later FPGA vision candidates integrated a camera and YOLO detection pipeline.

## Verification and Current Status

The CPU and system were checked with instruction-level and bare-metal simulation tests. CoreMark was ported and checked in short simulations; these are not official benchmark scores.

In one 160 × 90 diagnostic board test, ten consecutive detection packets passed CRC checks over UART. HDMI output did not lock on the display during that test; the external link issue requires further investigation. Different FPGA candidates have different validation status, and the final multi-object real-time version remains to be identified and verified.

**Tools and languages:** SystemVerilog, C, Python, Vivado simulation, RISC-V GCC and Pango Design Suite.

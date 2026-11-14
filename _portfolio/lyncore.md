---
title: "LynCore: RISC-V CPU and YOLO Integration"
excerpt: "A RISC-V CPU and FPGA vision system built around the Pango 100 Pro+ board and OV5640 camera."
collection: portfolio
permalink: /portfolio/lyncore/
---

## Overview

LynCore is a 32-bit RISC-V processor and system-on-chip project integrating accelerator control and a YOLO-based vision pipeline. The project uses the **Pango 100 Pro+ FPGA development board** (Meyesemi MES2L676-100HP, Pango PG2L100H) and an **OMNIVISION OV5640 camera** connected through an FMC daughterboard.

## Processor and System

- Five-stage, in-order RV32I pipeline with optional RV32M multiplication and division.
- Machine-mode exceptions and interrupts, UART, GPIO and timer peripherals.
- Optional two-way set-associative instruction and data caches and dynamic branch prediction.
- Bare-metal C startup and application support.

## Accelerator Integration

An AXI4-Lite control bridge, task configuration registers and C driver provide a basis for issuing accelerator jobs and polling their status. Earlier control-path tests used a simulated execution model; later FPGA vision candidates integrated the OV5640 camera and a YOLO detection pipeline.

## Verification and Test Results

- An earlier CPU/SoC validation phase recorded **676 core and system simulations**, including 600 instruction-level regression runs checking 61,416 committed instructions. These are simulation results, not FPGA performance figures.
- CoreMark was ported and checked in short simulations; these runs are not official benchmark scores.
- In a 160 × 90 diagnostic board test on 4 November 2026, **10 consecutive detection packets passed UART CRC checks**. The HDMI display reported no signal or an unsupported signal during that test.
- A separate RTL simulation checked 720p video timing without camera-frame input. It does not establish that HDMI output worked on the physical display. Different FPGA candidates have different validation status.

**Tools and languages:** SystemVerilog, C, Python, Vivado simulation, RISC-V GCC and Pango Design Suite.

## Source Code

[Download the diagnostic RTL source snapshot](/files/lyncore-diagnostic-rtl.zip)

This snapshot is intended for source inspection and does not include all
dependencies needed to build the complete FPGA project.

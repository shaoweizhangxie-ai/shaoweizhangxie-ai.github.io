---
title: "LynCore: RISC-V CPU and YOLO Accelerator Interface"
excerpt: "A five-stage RISC-V processor and SoC with a control interface for future YOLO accelerator integration."
collection: portfolio
permalink: /portfolio/lyncore/
---

## Overview

LynCore is a 32-bit RISC-V processor and minimal system-on-chip project developed for FPGA implementation. The project explores processor architecture, bare-metal software, and a control interface for coordinating with a YOLO accelerator.

## Processor and System

- Five-stage, in-order pipeline implementing RV32I, with optional RV32M integer multiplication and division.
- Machine-mode exception and interrupt handling, along with UART, GPIO, and timer peripherals.
- Optional two-way set-associative instruction and data caches and dynamic branch prediction.
- Bare-metal C startup and application support.

## YOLO Integration Interface

The system includes an AXI4-Lite control bridge, task configuration registers, and a C driver for issuing jobs and polling their status. Control-path simulations exercise successful completion, errors, and timeouts using a test execution model.

## Verification and Current Status

Processor and system functionality have been tested in simulation, including instruction-level checks and bare-metal software tests. CoreMark was ported and checked in short simulations; these runs do not constitute an official benchmark score.

The accelerator execution model is a test model and does not perform YOLO convolution or access DDR. Integration with real accelerator operators, end-to-end YOLO inference, and FPGA board validation remain future work.

**Tools and languages:** SystemVerilog, C, Python, Vivado simulation, RISC-V GCC.

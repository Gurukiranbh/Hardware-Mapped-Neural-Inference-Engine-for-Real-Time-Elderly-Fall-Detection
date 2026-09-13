# Hardware-Accelerated Real-Time Embedded Edge AI Fall Detection System

> Hardware-accelerated Edge AI system for real-time elderly fall detection using PSoC 5LP, ARM Cortex-M3, Verilog HDL, UDB MAC accelerator, and multi-sensor fusion.

## Overview

This project implements a real-time embedded Edge AI system for elderly fall detection on the Cypress PSoC 5LP System-on-Chip (SoC). It combines an ARM Cortex-M3 processor with a Verilog-based Multiply-Accumulate (MAC) accelerator synthesized into the Universal Digital Block (UDB) fabric, enabling hardware-accelerated neural inference without requiring an external FPGA or cloud processing.

The system acquires data from multiple sensors, performs feature preprocessing, executes a lightweight neural classifier, and detects four activity states in real time.

## Key Highlights

- Real-time Embedded Edge AI inference
- Verilog HDL hardware MAC accelerator
- Hardware-Software Co-Design
- ARM Cortex-M3 integration
- PSoC 5LP UDB hardware acceleration
- I²C multi-sensor fusion
- Fixed-point neural inference
- UART real-time monitoring
- LED fall-alert indication
- **2.27× faster hardware MAC execution** compared to software implementation

## System Architecture

```text
MPU6050 + BMP280 + KY-038
          │
         I²C
          │
     PSoC 5LP SoC
          │
 ┌─────────────────────┐
 │ ARM Cortex-M3       │
 │ • Sensor Processing │
 │ • Normalization     │
 │ • Argmax Classifier │
 │ • UART & LED        │
 └─────────┬───────────┘
           │
           ▼
 ┌─────────────────────┐
 │ Verilog UDB MAC     │
 │ Hardware Accelerator│
 └─────────┬───────────┘
           ▼
 Activity Classification
(Resting • Walking • Fall • Post-Fall)
```

## Hardware Components

| Component | Purpose |
|-----------|---------|
| PSoC 5LP | Main controller |
| ARM Cortex-M3 | Firmware execution |
| UDB Fabric | Hardware MAC accelerator |
| MPU6050 | Motion sensing |
| BMP280 | Pressure sensing |
| KY-038 | Sound sensing |
| UART | Debug output |
| LED | Fall alert |

## Technologies Used

### Programming

- Embedded C
- Verilog HDL

### Embedded Systems

- PSoC Creator
- ARM Cortex-M3
- Universal Digital Blocks (UDB)
- I²C
- UART
- ADC

### AI & Hardware

- Edge AI
- Embedded AI
- Neural Inference
- Fixed-Point Processing
- Sensor Fusion
- Hardware Acceleration

## Working Principle

1. Acquire real-time sensor data.
2. Normalize sensor values into an 8-bit feature vector.
3. Execute the neural MAC computation in UDB hardware.
4. Perform Argmax classification.
5. Output the detected activity through UART and LED.

## Performance

| Execution Path | Clock Cycles |
|----------------|-------------:|
| Software MAC | ~1016 |
| Hardware MAC | ~448 |

**Measured Hardware Speedup: 2.27×**

The hardware accelerator significantly reduces inference latency while maintaining identical classification results.

## Classification Output

The system detects four activity states:

- Normal Walking
- Resting
- Fall Detected
- Post-Fall

## Project Structure

```text
Firmware/
Verilog/
PSoC/
Testbench/
Results/
Documentation/
README.md
```

## Technical Contributions

- Designed a Verilog RTL MAC accelerator.
- Implemented hardware-software co-design on PSoC 5LP.
- Developed multi-sensor I²C acquisition firmware.
- Built a lightweight neural inference engine.
- Performed cycle-accurate hardware benchmarking.
- Achieved 2.27× hardware acceleration.

## Applications

- Elderly healthcare monitoring
- Wearable Edge AI devices
- Embedded Machine Learning
- Low-power AI systems
- Smart healthcare solutions

## Future Improvements

- Wireless emergency alerts
- Larger neural networks
- Additional sensor integration
- Power optimization
- Enhanced Edge AI capabilities

## Keywords

Embedded Systems • Edge AI • Embedded AI • Verilog HDL • RTL Design • Hardware Acceleration • PSoC 5LP • ARM Cortex-M3 • UDB • MAC Accelerator • I²C • UART • Sensor Fusion • Fixed-Point Processing • Real-Time Systems

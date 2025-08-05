# Small Fixed-Wing UAV Project

## Overview
This repository contains the design, control circuitry, firmware, and hardware assembly instructions for a small fixed-wing Unmanned Aerial Vehicle (UAV). The UAV supports remote control operation with a range of 500m–1km, automatic stabilization, GPS-based autonomous flight, and a return-to-home feature upon signal loss. The system is built around the STM32F103C8T6 microcontroller.

## Features
- **Remote Control**: 6 analog channels and 2 digital channels for precise control via an NRF24L01 module.
- **Flight Controller (FC)**:
  - Decodes control signals from NRF24L01 to manage 2 aileron servos, 1 rudder servo, 1 elevator servo, and 1 brushless motor ESC.
  - Reads UART signals from a GPS module for autonomous flight and return-to-home functionality.
  - Uses I2C IMU (ICM20948) for flight stabilization.
  - Supports firmware flashing and debugging via SWD.
  - Compatible with 2S–3S LiPo batteries, ensuring stable power delivery.
- **Flight Capabilities**:
  - Remote control with effective range of 500m–1km.
  - Automatic stabilization for smooth flight.
  - Autonomous flight via preloaded GPS waypoints.
  - Return-to-home feature on signal loss.

## Hardware Components
### Transmitter (TX) PCB
- **Function**: Captures 6 analog and 2 digital channels from user input.
- **Communication**: Transmits control signals via NRF24L01 module.

### Receiver (RX) PCB
- **Function**: Receives 6 PWM and 2 digital channels via NRF24L01.
- **Output**: Forwards signals to the Flight Controller.

### Flight Controller (FC)
- **Microcontroller**: STM32F103C8T6.
- **Peripherals**:
  - 2 aileron servos, 1 rudder servo, 1 elevator servo.
  - 1 ESC for brushless motor control.
  - GPS module (UART) for navigation.
  - ICM20948 IMU (I2C) for stabilization.
- **Power**: Supports 2S–3S LiPo batteries with stable power regulation.
- **Debugging**: SWD interface for firmware updates and debugging.

## Repository Structure
```
├── firmware/           # STM32F103C8T6 firmware source code
├── schematics/         # PCB schematics for TX, RX, and FC
├── software/           # Control software for autonomous flight and configuration
├── docs/               # Documentation for hardware assembly and setup
├── models/             # 3D models for UAV airframe
└── README.md           # This file
```

## Setup Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/uav-project.git
   cd uav-project
   ```

2. **Hardware Assembly**:
   - Refer to `/docs/assembly_guide.md` for detailed instructions on assembling the UAV airframe, TX, RX, and FC.
   - Ensure proper connections for NRF24L01, GPS, IMU, servos, and ESC as per `/schematics`.

3. **Firmware Installation**:
   - Install the STM32CubeIDE or compatible IDE.
   - Flash the firmware located in `/firmware` to the STM32F103C8T6 using an SWD debugger.
   - Configure the firmware settings for your GPS module and IMU calibration.

4. **Software Setup**:
   - Install the control software from `/software`.
   - Configure waypoints for autonomous flight using the provided interface.

5. **Testing**:
   - Test the TX-RX communication within a 500m range.
   - Verify stabilization using the IMU and autonomous flight with GPS.
   - Test return-to-home functionality by simulating signal loss.

## Requirements
- **Hardware**:
  - STM32F103C8T6 microcontroller.
  - NRF24L01 modules (TX and RX).
  - ICM20948 IMU.
  - GPS module with UART interface.
  - 2S–3S LiPo battery and compatible charger.
  - 2 aileron servos, 1 rudder servo, 1 elevator servo, 1 ESC, and a brushless motor.

- **Software**:
  - STM32CubeIDE for firmware development.
  - Python (for control software, if applicable).
  - Compatible OS: Windows, Linux, or macOS.

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact
For questions or suggestions, open an issue or contact [your email or GitHub handle].
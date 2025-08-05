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

### Flight Controller (FC)
- **Microcontroller**: STM32F103C8T6.
- **Function**: Receives 6 PWM and 2 digital channels via NRF24L01.
- **Peripherals**:
  - 2 aileron servos, 1 rudder servo, 1 elevator servo.
  - 1 ESC for brushless motor control.
  - GPS module (UART) for navigation.
  - ICM20948 IMU (I2C) for stabilization.
- **Power**: Supports 2S–3S LiPo batteries with stable power regulation.
- **Debugging**: SWD interface for firmware updates and debugging.


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

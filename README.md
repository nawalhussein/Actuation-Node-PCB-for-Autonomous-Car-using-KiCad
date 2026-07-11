# STM32 Actuator Control Board PCB

This project contains the complete hardware design (schematics and PCB layout) and associated software for a custom-built STM32-based actuator control system to be put in the autonomous car.

### Brief Project Description

This PCB is designed as a centralized control hub for multiple DC motor actuators in an autonomous or complex electro-mechanical system (e.g., an agribot, mobile robot, or robotic manipulator).

At its core is an STM32 "BluePill" microcontroller. The board interfaces with various components to manage complex movement:

* **Microcontroller:** An STM32F103 (BluePill) provides the processing logic.
* **Actuator Drivers:** Integrated circuits (represented by connectors in the current schematic iteration) control multiple DC motors with direction (`DIR`) and pulse-width modulation (`PWM`) speed signals.
* **Control Input:** It receives motion and velocity commands via a high-level **CAN bus** or standard **UART** serial communication.
* **Feedback (ADC):** Analog inputs monitor potentiometer-based sensors (e.g., steering and brake feedback) for precise position sensing.
* **Interface (DAC):** A Digital-to-Analog converter provides fine-tuned analog voltage output.
* **Level Shifting:** Bidirectional level shifters ensure logic compatibility between 3.3V signals (like `STEP_EN`, `DIR_REAR_BRAKE`) and other standard 5V peripherals.
* **Safety:** A robust protection circuit with a reverse-voltage blocking diode and a fast-acting fuse ensures system reliability.
* **Expandability:** Multiple power sources and extra GPIO headers are included for external sensor integration and future features.

---

### Project Repository Contents

* `/hardware/`: Kicad design files (schematic and PCB)
* `/docs/`: PDF for the PCB and schematic

![Crawling Robot](./4legs.png)

# Crawling Robot

A custom four-legged crawling robot built as a full mechatronics project, covering mechanical design, 3D printing, electronics integration, and embedded control.

The project is currently about 70% complete. The hardware components have been acquired, the mechanical design and 3D-printed assembly are complete, and the remaining work is focused on firmware, servo calibration, gait generation, and getting the robot to walk reliably.

## Project Highlights

- Designed and assembled a custom quadruped-style crawling robot platform.
- Uses 12 metal-gear servo motors for multi-joint leg movement.
- Includes a dedicated servo controller for stable PWM control.
- Adds an ESP32 as the onboard control and wireless-capable microcontroller.
- Integrates power regulation, switching, and safety-related components.
- Documents the build with rendered images, circuit diagrams, and assembly videos.

## Current Status

| Area | Status | Notes |
|------|--------|-------|
| Mechanical design | Complete | Robot body and leg structure designed for a 3D-printed build. |
| 3D printing | Complete | Printed parts are available for assembly. |
| Physical assembly | Complete | Assembly videos are included in this repository. |
| Components | Complete | Main components have been acquired, including the ESP32. |
| Circuit planning | Complete / refining | New and older circuit references are documented below. |
| Firmware | In progress | ESP32 control code and servo coordination are the next major task. |
| Walking gait | In progress | Servo calibration, leg sequencing, and stability testing are still required. |

## System Overview

The robot is built around a 12-servo leg system. Each leg uses multiple servos to create crawling motion, while the controller stack manages servo signals, power distribution, and future sensor input.

Planned control architecture:

| Layer | Component | Responsibility |
|-------|-----------|----------------|
| Main controller | ESP32 | High-level logic, wireless control, command handling, sensor input, and gait coordination. |
| Servo control | 18-channel servo controller | Generates stable PWM signals for the 12 servo motors. |
| Actuation | MG996R metal-gear servos | Drives the leg joints. |
| Power regulation | LM2596 buck converter | Helps manage voltage levels for electronics and servo power. |
| Safety/input | Toggle switch and limit switches | Manual power control and potential contact/end-stop feedback. |

## Media

### Robot Render

![Crawling Robot Render](./4legs.png)

### Assembly Videos

These videos show the physical assembly process and demonstrate the mechanical design work behind the project.

- [Assembly Video 1](./Video/Assembly-1.mp4)
- [Assembly Video 2](./Video/Assembly-2.mp4)
- [Assembly Video 3](./Video/Assembly-3.mp4)

## Circuit Diagrams

### New Circuit / Component Planning Diagram

![New Circuit Diagram](./new_diagrams.png)

### Older Circuit Reference

This older diagram is kept as a reference while the current electronics layout is refined.

![Old Circuit Diagram](./circuit.png)

## Bill of Materials

| No. | Component | Full Name / Description | Quantity | Cost / Notes |
|-----|-----------|--------------------------|----------|--------------|
| 1 | Microcontroller | ESP32 development board | 1 | Added to the project as the main controller. |
| 2 | Servo motor | MG996R metal-gear servo | 12 | RM 161.89 total recorded. |
| 3 | Servo controller | 18-channel servo controller | 1 | Used for driving the servo motors. |
| 4 | Power supply | 12V 3A DC power supply | 1 | Main external power source. |
| 5 | Voltage regulator | LM2596 DC-DC buck converter with voltmeter | 1 | Used to regulate voltage where needed. |
| 6 | Main switch | Mini toggle switch SPST | 1 | Manual power control. |
| 7 | Limit switch | Micro limit switch, 3-pin SPDT long hinge lever | 4 | For contact or end-stop sensing. |
| 8 | Protection | Rubber end caps | 4 | Mechanical protection for contact points. |
| 9 | Mechanical pin | 2 mm x 22 mm stainless steel dowel pin | 4 | Mechanical fastening and alignment. |
| 10 | Screws | M1.6 screw set | 120 | Mechanical assembly. |
| 11 | Screws | M2.5 screw set | 4 | Mechanical assembly. |
| 12 | Tester | Servo tester | 1 | Useful for manual servo testing and calibration. |

## Development Roadmap

The remaining work is focused on bringing the hardware to life through software and testing.

1. Create ESP32 firmware project structure.
2. Map each servo channel to the correct leg and joint.
3. Calibrate servo center positions and safe movement limits.
4. Build basic single-servo and single-leg motion tests.
5. Implement a crawling gait sequence.
6. Add wireless control or command input through the ESP32.
7. Test power stability while multiple servos move under load.
8. Record a walking demo and update this README with final results.

## Engineering Notes

- The servo power rail should be handled separately from sensitive logic power where possible.
- All controller boards and servo power references should share a common ground.
- The servo controller jumper and servo power wiring should be checked carefully before powering the full robot.
- Initial testing should start with one servo, then one leg, before moving all 12 servos together.
- Servo current draw can spike during movement, so power stability should be tested before full walking trials.

## Repository Structure

```text
.
|-- readme.md
|-- 4legs.png
|-- new_diagrams.png
|-- circuit.png
`-- Video/
    |-- Assembly-1.mp4
    |-- Assembly-2.mp4
    `-- Assembly-3.mp4
```

## Reference

This project uses the following project as one of its references and inspirations:

https://github.com/almelnz2005/hexapod/tree/main

# Four-Legged Crawling Robot for HVAC Duct Inspection

<p align="center">
  <img src="Render%20Photos/isometric.png" alt="Isometric CAD render of the four-legged crawling robot" width="850">
</p>

This repository showcases a custom four-legged crawling robot developed for industrial HVAC duct inspection. The robot is designed as a compact, tethered mechatronics platform that can enter rectangular duct environments and support remote visual inspection, LED illumination, and gas-presence early warning.

The current prototype focuses on the mechanical platform, 3D-printed assembly, electronics integration, servo actuation, and early control architecture for crawling gait development.

## Project Overview

Industrial HVAC ducts can be narrow, dusty, poorly lit, and difficult to inspect safely. This project explores a crawling robotic platform that reduces the need for direct human entry while giving the operator a live view of the duct interior.

The selected design uses four articulated legs instead of a wheel-only platform. Each leg has three servo-driven joints, giving the robot a total of 12 actuated degrees of freedom for crawling motion, stance control, and in-place turning.

## Key Features

- Four-legged crawling architecture for confined duct inspection
- 12 MG996R metal-gear servo motors for multi-joint leg movement
- Modular PETG and PLA 3D-printed mechanical structure
- Front-mounted camera for real-time visual inspection
- LED illumination for low-light duct environments
- MQ-2 gas sensor for non-certified gas-presence early warning
- ESP32-based low-level motion control
- Raspberry Pi 4-oriented high-level processing architecture
- Dedicated multi-channel servo controller for stable PWM output
- Tethered operation concept for reliable communication and emergency retrieval

## Current Prototype Status

| Area | Status | Notes |
| --- | --- | --- |
| CAD design | Complete | Full robot, leg modules, and power-module mounting were modeled. |
| 3D printing | Complete | PETG and PLA parts were printed for the physical prototype. |
| Mechanical assembly | Complete | Four-leg structure and main body have been assembled. |
| Electronics integration | In progress | Servo controller, wiring, power regulation, and sensor layout are being refined. |
| Servo calibration | In progress | Joint limits and neutral positions must be tuned before full gait testing. |
| Crawling gait | In progress | Locomotion sequencing and stability testing are the next development focus. |

## System Architecture

| Layer | Main Components | Role |
| --- | --- | --- |
| Mechanical platform | PETG/PLA body, four modular legs, brackets, fasteners | Supports the robot structure and protects the electronics. |
| Actuation | 12 MG996R metal-gear servos | Drives hip, knee, and foot/ankle motion for each leg. |
| Servo control | Multi-channel servo controller | Generates stable PWM signals for coordinated leg movement. |
| Low-level controller | ESP32 | Handles gait timing, command execution, and sensor input. |
| High-level processing | Raspberry Pi 4 | Intended for video streaming, interface, logging, and future computer vision. |
| Inspection payload | Camera, LED lighting, MQ-2 sensor | Provides visual inspection and gas-presence early warning. |
| Power | 12 V DC supply, buck converter, power switching | Regulates power for servos, controllers, and sensors. |
| Communication | Tethered connection concept | Improves reliability in metallic duct environments and supports retrieval. |

## CAD and Prototype Gallery

### Rendered CAD Views

| Isometric | Front | Top |
| --- | --- | --- |
| <img src="Render%20Photos/isometric.png" alt="Isometric render" width="260"> | <img src="Render%20Photos/front.png" alt="Front render" width="260"> | <img src="Render%20Photos/top.png" alt="Top render" width="260"> |

| Left | Right | Back |
| --- | --- | --- |
| <img src="Render%20Photos/left.png" alt="Left render" width="260"> | <img src="Render%20Photos/right.png" alt="Right render" width="260"> | <img src="Render%20Photos/back.png" alt="Back render" width="260"> |

### Assembly Documentation

| Complete Robot Drawing | Leg Assembly Drawing | Exploded Main Assembly |
| --- | --- | --- |
| <img src="Sketching%20Diagrams/Complete%20Assembled.png" alt="Complete assembled drawing" width="260"> | <img src="Sketching%20Diagrams/Leg.png" alt="Leg schematic drawing" width="260"> | <img src="Explode%20and%20Non-exploded%20models/Explode%20Main%20Assembled.png" alt="Exploded main assembly" width="260"> |

### Physical Prototype

| Front View | Electronics and Buck Converter |
| --- | --- |
| <img src="Finished%20Project/Robot%20front.jpg" alt="Finished robot front view" width="330"> | <img src="Finished%20Project/Robot%20with%20buck%20converter.jpg" alt="Finished robot with buck converter" width="330"> |

## Assembly Videos

The project includes assembly videos documenting the physical build process:

- [Assembly Video 1](Video/Assembly-1.mp4)
- [Assembly Video 2](Video/Assembly-2.mp4)
- [Assembly Video 3](Video/Assembly-3.mp4)

## Main Components

| Component | Quantity | Purpose |
| --- | ---: | --- |
| MG996R metal-gear servo motor | 12 | Leg joint actuation |
| ESP32 development board | 1 | Low-level control and command handling |
| Raspberry Pi 4 | 1 | High-level processing and video-oriented architecture |
| Multi-channel servo controller | 1 | PWM generation for servo control |
| DC-DC buck converter | 1 | Voltage regulation for electronics and servo system |
| Camera module | 1 | Live visual inspection |
| LED lighting | 1 set | Illumination inside dark duct spaces |
| MQ-2 gas sensor | 1 | Gas-presence early warning |
| 3D-printed PETG/PLA structure | 1 set | Robot body, legs, brackets, and mounts |

## Development Roadmap

1. Finalize electronics mounting and cable routing.
2. Calibrate all servo neutral positions and safe angle limits.
3. Validate one-servo, one-leg, and four-leg motion tests.
4. Develop stable crawling gait sequences.
5. Test power stability during multi-servo movement.
6. Integrate live video, LED control, and MQ-2 warning feedback.
7. Perform controlled duct-environment movement testing.
8. Record a complete walking and inspection demonstration.

## Contributors

Project contributor profiles are available here:

[https://idp1.carrd.co/](https://idp1.carrd.co/)

Project team:

- Muhammad Naufal Hakimi Bin Irwan Affandi
- Ahmad Nizar Bin Amzah
- Abdullah Hasan Bin Sidek
- Amir Farhan Bin Ghaffar
- Azmi Bin Basharudin

## Notes

- The MQ-2 module is used as an early-warning sensor only and is not a certified gas-safety instrument.
- The robot is a development prototype; reliable crawling performance depends on servo calibration, gait tuning, and testing.
- Report documents, brochure drafts, and internal submission files are intentionally excluded from this public showcase repository.

## Reference

This project was also inspired by open-source legged robot and hexapod development work, including:

[almelnz2005/hexapod](https://github.com/almelnz2005/hexapod/tree/main)

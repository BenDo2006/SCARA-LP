# SCARA-LP: Modular SCARA Robotic Platform

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/20f5dd88dd745c8543defd34b2ca98524a1d10c3/SCARA_LP_CoverImage.png" width="600"/>
</p>

<p align="center">
  <em>Figure 1: SCARA-LP modular robotic platform in assembled configuration.</em>
</p>

## System Overview
SCARA-LP is a modular 3-DOF SCARA robotic platform designed to integrate mechanical, electrical, and control subsystems into a single functional system. It consists of a belt-driven 2-DOF arm with a Z-axis end effector, powered by DC motors with encoder feedback and controlled through a custom motor driver and microcontroller architecture. The platform is built for automation, testing, and iterative prototyping, with a focus on precise positioning, repeatability, maintainability, and real-world electromechanical integration and debugging.

## Key Features
- Modular mechanical design for easy assembly, maintenance, and iterative upgrades  
- Open control architecture exposing motor control inputs and encoder signals for external microcontroller integration  
- Belt-driven transmission system optimized for low backlash, smooth motion, and consistent repeatability  
- Limit switch integration for homing, safety constraints, and system protection  
- Integrated electromechanical system including custom PCB, motor driver, and sensor interfaces  
- Designed for hands-on assembly, testing, troubleshooting, and repair of mechanical, electrical, and control components  

## Design Considerations
- Belt drive selected over gear and chain systems to reduce backlash and enable smoother motion  
- Motors positioned at the base to reduce inertia at distal links and improve dynamic response  
- Limit switches integrated to enable repeatable homing and protect against overtravel  
- System designed to expose control and feedback interfaces for external controller integration  

## System Specifications

| Parameter | Value | Unit |
|----------|------|------|
| Shoulder Link Length (L1) | 142 | mm |
| Elbow Link Length (L2) | 130 | mm |
| Max Reach | 272 | mm |
| Min Reach | 12 | mm |
| Joint 1 Range | ±90 | ° |
| Joint 2 Range | ±145 | ° |
| Z-axis Stroke | 36.7 | mm |
| Planar Work Area | 115,800 | mm² |

## Work Envelope
The SCARA-LP workspace is defined by link lengths and joint constraints, resulting in a non-uniform reachable area with inner dead zones characteristic of SCARA kinematics.

<p align="center">
  <img src="https://github.com/BenDo2006/SCARA-LP/blob/337f11f11f19b03a7d8ee583dbd28d7765d897f3/SCARA_WorkEnvelope_Visual.png" width="600"/>
</p>
<p align="center">
  <em>Figure 2: SCARA work envelope showing reachable workspace (white region) and kinematic dead zones (red regions) defined by link constraints.</em>
</p>

## Results & Improvements

- Increased effective workspace by **85%** (536 mm² to 990 mm²) through kinematic optimization of link parameters  
- Improved motion consistency and repeatability by diagnosing and correcting belt tension, pulley alignment, and mechanical vibration  
- Reduced end-effector inertia by relocating motors to the base, improving dynamic response and system stability  
- Validated system behavior using MATLAB simulations and a custom Desmos-based visualization tool  

## Project Scope
This repository provides the mechanical design, system architecture, and supporting documentation required to understand and reproduce the SCARA-LP platform. It includes CAD models, electrical schematics, and system-level documentation.
Control implementation is intentionally left open, as the platform is designed to support external microcontroller and motor driver integration.

## Maintenance & Troubleshooting
- Motion latency → Inspect and clean belt/pulley system  
- Increased joint friction → Check bearing condition and apply lubrication  
- Motor rotates but arm does not → Inspect transmission and coupling integrity  

## Documentation
- [Mechanical Assembly Documentation (PDF)](link_here)

## License

© 2026 Ben Do. All rights reserved.

This project is licensed under the SCARA Non-Commercial License (v1.0).  
Free for personal, educational, and research use. Commercial use requires explicit permission.

For licensing inquiries: bendowork2006@gmail.com

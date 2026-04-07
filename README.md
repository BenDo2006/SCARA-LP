# SCARA-LP: Modular SCARA Robotic Platform

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/20f5dd88dd745c8543defd34b2ca98524a1d10c3/SCARA_LP_CoverImage.png" width="600"/>
</p>

<p align="center">
  <em>Figure 1: SCARA-LP modular robotic platform in assembled configuration.</em>
</p>

<p align="center">
  <strong>Modular. Open. Built for real-world debugging and control.</strong>
</p>

---

## Overview

> Designed, built, and iteratively debugged as a complete electromechanical system with emphasis on real-world failure modes and system integration.

SCARA-LP is a modular 3-DOF SCARA robotic platform designed as a fully integrated electromechanical system for automation, testing, and iterative prototyping. The system features a belt-driven 2-DOF arm with a Z-axis end effector, powered by DC motors with encoder feedback and controlled through a custom motor driver and microcontroller architecture.

The platform emphasizes **open control architecture**, **maintainability**, and **real-world troubleshooting**, allowing direct access to motor control signals and encoder channels for external controller integration and user-defined control implementation.

---

## System Architecture

<p align="center">
  <img src="https://github.com/BenDo2006/SCARA-LP/blob/c1aff60bb12e8d9277f278d14365f4c2e975072c/System_Architecture_SCARA.drawio.png" width="600"/>
</p>

<p align="center">
  <em>Figure 2: System-level block diagram illustrating control, sensing, actuation, and power flow within the SCARA-LP platform.</em>
</p>

**Legend:**
- Blue: Control
- Orange: Actuation / Drive
- Green: Mechanical Structure
- Purple: Sensing / Feedback
- Yellow: Power

The system is structured around an open architecture where encoder feedback and control signals interface directly with the microcontroller, which commands the motor driver to actuate the system. Power is distributed across all subsystems, while limit switches provide safety and homing feedback.

---

## What Makes It Different

- **Open control architecture** — direct access to motor inputs and encoder signals  
- **Designed for debugging** — built to be tested, tuned, and repaired  
- **System-level integration** — mechanical, electrical, and control subsystems unified  
- **Modular design** — easy to assemble, modify, and iterate  

---

## System Capabilities

- Precise planar positioning using SCARA kinematics  
- Closed-loop feedback using encoder signals  
- External microcontroller and motor driver integration  
- Repeatable homing and safety using limit switches  
- Smooth motion through optimized belt-driven transmission  

---

## Engineering Highlights

- Increased effective workspace by **85%** through kinematic optimization  
- Diagnosed and resolved real mechanical issues including belt tension, misalignment, and backlash  
- Improved system stability by redesigning mass distribution and motor placement  
- Validated system behavior using MATLAB simulations and a custom Desmos visualization tool  

---

## Engineering Challenges & Fixes

- **Belt tension instability:**  
  Observed inconsistent motion and positional drift due to improper belt preload. Resolved through iterative tension tuning and pulley alignment, restoring smooth and repeatable motion.

- **Backlash from shaft coupling:**  
  Identified loss of torque transmission due to slipping D-shaft interface. Redesigned coupling interface to improve engagement and reduce backlash.

- **Vibration during motion:**  
  Caused by belt compliance and mass distribution. Mitigated by relocating motors to the base and improving structural stability and reducing rotational inertia.

- **Mechanical vs control ambiguity:**  
  Distinguished between control delay and mechanical response issues by isolating encoder feedback and physical system behavior during testing.

---

## Design Decisions & Tradeoffs

- **Belt drive vs gear/chain:** selected for low backlash, reduced weight, and ease of assembly, accepting reduced stiffness due to compliance  
- **Motor placement at base:** reduces distal inertia and improves dynamic response  
- **Open signal access:** enables external controller integration and experimentation  
- **Limit switches:** provide reliable homing and mechanical overtravel protection  

---

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

---

## Work Envelope

The SCARA-LP workspace is defined by link lengths and joint constraints, resulting in a non-uniform reachable area with inner dead zones characteristic of SCARA kinematics.

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/337f11f11f19b03a7d8ee583dbd28d7765d897f3/SCARA_WorkEnvelope_Visual.png" width="600"/>
</p>

<p align="center">
  <em>Figure 3: SCARA work envelope showing reachable workspace (white) and kinematic dead zones (red) defined by link constraints.</em>
</p>

### Interactive Visualization
Explore parameterized SCARA workspace behavior:

[View Interactive Model (Desmos)](https://www.desmos.com/calculator/pglkq3bcid)

---

## Electrical System

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/c85d4bc51b07f15943d7265d01a575630cb0f7d4/Simplified_PCB_Render.png" width="500"/>
</p>

<p align="center">
  <em>Figure 4: Custom PCB showing key components including motor driver interface, encoder inputs, limit switch connections, and power routing.</em>
</p>

The PCB was designed by **Alex Dawson**, with system integration and interfacing handled as part of this project.

The custom PCB serves as a centralized interface for motor control, sensor input, and power distribution. It integrates an H-bridge motor driver for actuator control, encoder and limit switch inputs for feedback and safety, and onboard protection via a fuse.

The architecture is intentionally designed to be **open and modular**, exposing motor control and feedback signals to allow users to interface their own external microcontrollers and motor drivers. The microcontroller mount is positioned centrally to simplify wiring and improve system organization.

### Electrical Documentation
- [PCB Design & Schematic (PDF)](link_here)

---

## Maintenance & Troubleshooting

| Symptom / Diagnosis | Likely Cause | Recommended Action |
|-------------------|-------------|--------------------|
| Delayed or inconsistent motion response | Debris buildup or improper belt tension | Clean belt and pulleys; re-tension belt using idle pulley |
| Jerky or uneven motion | Belt misalignment or uneven tension | Realign pulleys and ensure consistent belt tension |
| Excessive backlash or lost motion | Belt slack or worn belt teeth | Re-tension or replace belt |
| Increasing positional inaccuracy | Belt stretch, encoder misalignment, or loose fasteners | Recalibrate system and inspect components |
| Increased joint friction | Bearing wear or lack of lubrication | Lubricate or replace bearings |
| Grinding or abnormal noise | Bearing failure or contamination | Replace bearings and clean housing |
| Motor rotates but arm does not move | Belt slip or coupling failure | Inspect and secure transmission components |
| Sudden increase in backlash | Shaft interface wear (e.g., D-shaft slipping) | Repair or redesign coupling |
| Inconsistent homing | Misaligned or faulty limit switches | Realign or replace switches |

---

## Project Scope

This repository provides the mechanical design, system architecture, and supporting documentation required to understand and reproduce the SCARA-LP platform. It includes CAD models, electrical schematics, and system-level documentation.

Control implementation is intentionally left open to support external microcontroller and motor driver integration.

---

## Documentation

- [Mechanical Assembly Documentation (PDF)](link_here)

---

## License

© 2026 Ben Do. All rights reserved.

This project is licensed under the SCARA Non-Commercial License (v1.0).  
Free for personal, educational, and research use. Commercial use requires explicit permission.

For licensing inquiries: bendowork2006@gmail.com

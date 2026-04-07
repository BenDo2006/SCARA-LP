# SCARA-LP: Modular SCARA Robotic Platform

- Designed and built a modular SCARA robotic arm integrating mechanical, electrical, and control systems  
- Increased reachable workspace by **85% (536 to 990 mm²)** through kinematic optimization  
- Diagnosed and resolved real mechanical issues including belt tension, misalignment, backlash, and vibration  

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/20f5dd88dd745c8543defd34b2ca98524a1d10c3/SCARA_LP_CoverImage.png" width="600"/>
</p>

<p align="center">
  <em>SCARA-LP modular robotic platform in assembled configuration.</em>
</p>

---

## Overview

SCARA-LP is a modular 3-DOF robotic platform developed as a complete electromechanical system for automation, testing, and iterative prototyping.

The system uses a belt-driven 2-DOF arm with a Z-axis end effector, powered by DC motors with encoder feedback and controlled through a custom motor driver and microcontroller architecture.

The design emphasizes **debuggability, maintainability, and open control access**, enabling direct interaction with motor control signals and encoder feedback for system tuning and external controller integration.

---

## System Architecture

<p align="center">
  <img src="https://github.com/BenDo2006/SCARA-LP/blob/c1aff60bb12e8d9277f278d14365f4c2e975072c/System_Architecture_SCARA.drawio.png" width="600"/>
</p>

<p align="center">
  <em>System-level architecture showing control, sensing, actuation, and power flow.</em>
</p>

The architecture enables direct access to encoder feedback and motor control signals, allowing precise debugging and flexible control integration. Limit switches provide reliable homing and safety, while power is distributed across all subsystems.

---

## Engineering Highlights

- Increased effective workspace by **85%** through kinematic optimization  
- Diagnosed and resolved mechanical issues including belt tension, misalignment, and backlash  
- Improved system stability through mechanical redesign and mass distribution  
- Validated system behavior through simulation and physical testing  

---

## Maintenance & Troubleshooting

| Symptom / Diagnosis | Likely Cause | Recommended Action |
|-------------------|-------------|--------------------|
| Delayed or inconsistent motion response | Improper belt tension or debris | Clean system and re-tension belt |
| Jerky or uneven motion | Belt misalignment or uneven tension | Realign pulleys and adjust tension |
| Excessive backlash or lost motion | Belt slack or worn components | Re-tension or replace belt |
| Increasing positional inaccuracy | Belt stretch or encoder misalignment | Recalibrate and inspect system |
| Increased joint friction | Bearing wear or lack of lubrication | Lubricate or replace bearings |
| Grinding or abnormal noise | Bearing failure or contamination | Replace bearings and clean system |
| Motor rotates but no motion | Belt slip or coupling failure | Inspect and secure drivetrain |
| Sudden backlash increase | Shaft interface wear | Redesign or reinforce coupling |
| Inconsistent homing | Faulty or misaligned limit switches | Realign or replace switches |

---

## Design Decisions & Tradeoffs

- **Belt drive vs gear/chain:** chosen for low backlash and ease of assembly, accepting reduced stiffness  
- **Motor placement at base:** reduces inertia and improves dynamic response  
- **Open signal access:** enables external controller integration and real-time debugging  
- **Limit switches:** ensure reliable homing and mechanical safety  

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

## Bill of Materials (BOM)

A structured Bill of Materials was developed to support assembly, manufacturing, and system integration.

### BOM Preview

<p align="center">
  <a href="https://bcit365-my.sharepoint.com/:x:/r/personal/bdo9_my_bcit_ca/Documents/SCARA_MK_I_BOM.xlsx?d=w0ce96e64e2ec4a02ad57fd1eef0aa47b&csf=1&web=1&e=IQwKGl&nav=MTVfezAwMDAwMDAwLTAwMDEtMDAwMC0wMDAwLTAwMDAwMDAwMDAwMH0">
    <img src="https://github.com/BenDo2006/SCARA-LP/blob/dd62c8d3cb93007295c1c66b4025952f761ef681/BOM_Preview.png" width="1000"/>
  </a>
</p>

<p align="center">
  <em>Click on the BOM Preview above to access the spreadsheet</em>
</p>

---

## Work Envelope

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/337f11f11f19b03a7d8ee583dbd28d7765d897f3/SCARA_WorkEnvelope_Visual.png" width="600"/>
</p>

<p align="center">
  <em>Reachable workspace (white) and kinematic dead zones (red).</em>
</p>

[View Interactive Model (Desmos)](https://www.desmos.com/calculator/pglkq3bcid)

---

## Electrical System

<p align="center">
  <img src="https://raw.githubusercontent.com/BenDo2006/SCARA-LP/c85d4bc51b07f15943d7265d01a575630cb0f7d4/Simplified_PCB_Render.png" width="500"/>
</p>

<p align="center">
  <em>Custom PCB for motor control, encoder input, and power distribution.</em>
</p>

The PCB integrates motor driver interfaces, encoder inputs, limit switch connections, and power routing. The architecture is modular, allowing external microcontrollers and drivers to be used for flexible control development.

---

## Project Scope

This repository includes mechanical design, system architecture, and documentation required to understand and reproduce the SCARA-LP platform.

---

## Documentation

- [Mechanical Assembly Documentation (PDF)](link_here)  
- [PCB Design & Schematic (PDF)](link_here)

---

## License

© 2026 Ben Do. All rights reserved.  
Free for personal and educational use. Commercial use requires permission.

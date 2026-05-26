# Autonomous EV3 Navigation & Forklift Robot

## Project Overview
This repository documents the design, programming, and testing of an autonomous mobile robot built using the LEGO Mindstorms EV3 platform and programmed via LabVIEW. Developed as a collaborative engineering design project, the robot was engineered to autonomously traverse complex tracks (including solid and dashed curved lines), interact with specialized cargo infrastructure, and dynamically identify container contents based on weight-to-motor-strain analytics.

The project successfully met structural subtasks and advanced to the final track demonstration.

---

## Team & Contributions
Developed by **Group 1.15** (ENED 1002C):
*   **Christoph Simms** – Subtask 1 Lead, Project Status Manager, Core Mechanical Assembly & Structural Rework.
*   **Cooper Hornaday** – Navigation System Architecture, Code of Cooperation Author, Final Deliverables Controller.
*   **Ben Eberhardt** – Inventory Management, Teaming & Reflection Lead, Mechanical Lift System Design.
*   **Dane Moore** – LabVIEW Environment Calibration, Design Specifications Analyst, Final Demo Quality Assurance.

---

## Engineering Design Process & Methodology

### 1. Requirements & System Constraints
The robot architecture was strictly bound by specific engineering guidelines and hardware limitations:
*   **Port Constraints:** Restricted to 4 available input slots for sensory equipment and 4 output ports for motorized operations.
*   **Target Performance Criteria:** Strict operational metrics including minimizing deviation on straight segments ($<10\text{ cm}$), ensuring a battery operational lifespan of $>1\text{ hour}$, and maintaining an efficient run success rate of $9/10$.

### 2. Subsystem Architecture

#### Navigation & Line-Following
*   **Chassis Kinematics:** Implemented a highly agile 3-point configuration utilizing two front wheels connected to isolated, independent motors paired with a rear ball bearing. This design enabled a zero-radius $360^\circ$ turning capability.
*   **Sensor Array:** Engineered a dual color-sensor array positioned exactly $1\text{ inch}$ above the track surface. The software logic cross-analyzed differential light reflectance thresholds to prevent track-loss across sharp angles.

#### Mechanical Lifting & Predictive Analysis
*   **Forklift Mechanism:** Constructed a rigid gear-driven forklift assembly powered by an independent auxiliary motor. 
*   **Data-Driven Content Identification:** Programmed a predictive algorithmic loop within LabVIEW. By reading real-time motor power fluctuations and scaling strain values during the initial lift sequence, the robot mathematically classified whether cargo contents were "Light" ($0\text{--}50\text{ g}$) or "Heavy" ($100\text{--}150\text{ g}$).

---

## Verification & Empirical Testing Data

Dynamic system testing was conducted across multiple trials to validate mechanical and programmatic reliability before the final deployment:

*   **Straight Line Stability:** Achieved an empirical mean deviation of just $6\text{ cm}$ over a $3\text{-meter}$ sprint, safely meeting the $<10\text{ cm}$ constraint threshold.
*   **Rotational Precision:** Multi-trial angular testing confirmed full-circle rotational turns calibrated to a precise $5^\circ$ error margin.
*   **Reflectance Calibration:** Sensor parameters were iteratively processed using MATLAB data arrays to successfully isolate target reflective value differences across distinct lighting environments.
*   **Load Limit Verification:** Validated structural lifting capabilities through incremental $50\text{g}$ payload testing up to a maximum design constraint limit of $150\text{ grams}$.

---

## Repository Structure
```text
├── Documentation/
│   └── Activity_DN_Team1.15.pdf      # Verbatim technical engineering notebook
├── Source_Code/
│   ├── Path_Following_Logic.vi        # LabVIEW dual-sensor line tracking code
│   ├── Forklift_Control.vi            # Motorized lift and drop-off sequences
│   └── Weight_Classification.vi       # Motor strain analysis predictive script
├── System_Architecture/
│   ├── Functional_Block_Diagram.png   # I/O port schematics and EV3 brick layout
│   └── Orthographic_Sketches/         # Structural CAD blueprints and layout sheets
└── Test_Logs/
    └── Empirical_Trial_Data.xlsx      # Deviation, angle, and load capacity results

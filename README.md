---
# Kinematics Lab
### An Interactive Robot Manipulator Simulator for Education and Code Testing

A web-based toolkit for forward/inverse kinematics, trajectory planning, pick-and-place, and whiteboard drawing with robotic manipulators — built for the
ME/CDS/EE 235a Advanced Robotics course at Caltech.

**▶ [Full Demo Video (YouTube)](https://www.youtube.com/watch?v=RkBm2ltJWgI)**

---

## Overview

Kinematics Lab is a comprehensive, interactive simulator that runs as a **single self-contained HTML file** in any modern web browser — no installation,
compilation, or server required. It accurately models the Universal Robots **UR10e, UR5e, and UR3e** collaborative robot arms, as well as simplified 2-DOF and
3-DOF educational models, using the standard **Denavit–Hartenberg (DH) parameterization**.

The simulator was built to provide a zero-friction educational tool where students can immediately explore the spatial concepts underlying robotic manipulation:
forward kinematics, inverse kinematics, Jacobian-based velocity control, trajectory planning, and collision detection — all through interactive 3D visualization.
It also emulates the **python-urx** API, so control scripts developed in the simulator can transfer directly to real UR hardware.

---

## Features

### Four Operating Modes

**Learn Mode**
- 11 interactive lessons organized into four chapters: Fundamentals, Kinematics, Dynamics/Motion Control, and Programming
- Topics include DH parameters, homogeneous transforms, FK, IK, velocity kinematics, trajectory planning, python-urx programming, IK for drawing, and safety
- The 3D viewport auto-configures for each concept (e.g., enabling coordinate frames for the DH lesson, enabling trace for FK)

**Play Mode**
- Direct joint-angle control via sliders and numeric inputs
- Real-time FK computation and transformation matrix display
- End-effector tracking, coordinate frame visualization, and gripper control
- Object pick-and-place with simple rigid-body physics (gravity, bounce, friction)

**Simulate Mode**
- Code editor supporting **JavaScript** (`update(t)` continuous control functions) and **Python-urx** syntax (`movej`, `movel`, gripper commands)
- Real-time 3D execution with live console output
- Full python-urx API emulator for seamless transfer to real hardware

**Draw Mode**
- Whiteboard-drawing laboratory: the robot holds a pen and draws on a flat surface
- Supports direct `rob.movej()` joint commands or Cartesian `draw_to(x, y)` commands with automatic IK
- Straight-line Cartesian paths solved via **damped least-squares (Levenberg–Marquardt) numerical IK**
- Tool-down orientation constraint enforced throughout; aspect ratio correction included

---

## Technical Details

| Component | Details |
|-----------|---------|
| **Rendering** | Three.js (r128) — hardware-accelerated 3D with shadows, PBR materials, orbit controls |
| **Kinematics** | Standard DH convention; parameters sourced from Universal Robots official documentation |
| **IK Solver** | Damped least-squares (Levenberg–Marquardt) numerical IK for draw mode |
| **Collision Detection** | Floor/table, self-collision, and object collision |
| **Physics** | Simple rigid-body simulation (gravity, bounce, friction) for object interaction |
| **Robot Models** | UR10e, UR5e, UR3e (full 6-DOF), 2-DOF planar, 3-DOF spatial |
| **API Emulation** | python-urx (`movej`, `movel`, `gripper.move`, `time.sleep`) |
| **Dependencies** | None — vanilla JavaScript + Three.js, runs in any modern browser |

---

## Usage

1. Download or clone this repository
2. Open `KinematicsLab.html` in any modern web browser
3. Select a mode from the top menu and start exploring

No build step, no server, no installation required.

---

## Robot Models

- **UR10e** — 6-DOF, 1300 mm reach, 12.5 kg payload
- **UR5e** — 6-DOF, 850 mm reach, 5 kg payload
- **UR3e** — 6-DOF, 500 mm reach, 3 kg payload
- **2-DOF Planar** — Simplified educational model
- **3-DOF Spatial** — Simplified educational model

All UR models use DH parameters sourced from Universal Robots' official documentation.

---

## Demo

![Kinematics Lab Draw Mode](assets/KinematicsLab_DrawHIDemo.gif)

*Draw Mode: the robot arm drawing "Hi" on the whiteboard using Cartesian `draw_to(x, y)` commands solved via numerical IK.*

---

## Course

Built as the final project for **ME/CDS/EE 235a — Advanced Robotics: Kinematics** at the California Institute of Technology, March 2026.

The full project report is available in this repository:
[`JonasHansen_KinematicsLab_ProjectReport.pdf`](assets/JonasHansen_KinematicsLab_ProjectReport.pdf)

---

## Author

**Jonas Hansen** — California Institute of Technology


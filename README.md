# CPC354 - Computer Graphics (Assignment 2)

This repository contains the WebGL interactive 3D simulation implementation and PDF report for **CPC354: Computer Graphics - Assignment 2** (Semester 1, Academic Session 2025/2026) at Universiti Sains Malaysia (USM).

## Course Details
- **Course Code:** CPC354
- **Course Name:** Computer Graphics
- **Semester:** Semester 1, Year 3 (2025/2026)
- **Project Title:** Interactive 3D Robotic Arm Simulation

---

## Assignment Overview

The assignment is a WebGL-based interactive 3D simulation representing a Robotic Arm with multiple joints:
- **WebGL Application (`RoboticArm_Final.html`):** Renders a 3D robotic arm model with segment hierarchies (base, upper arm, lower arm, fingers/claws).
- **Hierarchical Modeling:** Computes joint angles, relative transformations, and matrices to simulate a robotic system where moving a parent joint affects child segments appropriately.
- **Controls & Interactions:** Allows users to rotate joints, extend sections, open/close claws, adjust light sources, toggle wireframe views, and change camera angles (orthographic vs. perspective projections) in real-time.

---

## What I Did
- Developed the complete WebGL-based robotic arm rendering, shader integration, and controls in [`RoboticArm_Final.html`](RoboticArm_Final.html).
- Calculated transformation hierarchies, lighting models (ambient, diffuse, specular), and rendering pipelines.
- Wrote the group report covering system design, coordinate transformations, and control mappings: [`CPC354 Assignment 2 Report.pdf`](CPC354%20Assignment%202%20Report.pdf).
- Consolidated the original assignment guideline: [`ASSI2-CPC354.pdf`](ASSI2-CPC354.pdf).

---

## Tools & Tech Stack
- **Languages:** JavaScript, HTML, CSS, GLSL
- **Framework:** Native WebGL (WebGL 1.0/2.0 APIs)

---

## How to Run

1. Open [`RoboticArm_Final.html`](RoboticArm_Final.html) in any modern web browser supporting WebGL.
2. Use the interactive buttons/sliders or keyboard hotkeys (described in the UI or report) to control:
   - Base rotation
   - Joint angles (shoulder, elbow, wrist)
   - Claw opening/closing
   - Lighting angles and camera views

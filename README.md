# CPC354 - Computer Graphics (Assignment 2)

<p align="center">
  <img src="https://img.shields.io/badge/Language-WebGL%20%26%20JS-990000?style=for-the-badge&logo=webgl&logoColor=white" alt="Language" />
  <img src="https://img.shields.io/badge/Course-CPC354-24292e?style=for-the-badge" alt="Course" />
  <a href="https://github.com/ahmedtags">
    <img src="https://img.shields.io/badge/Profile-ahmedtags-D9A34A?style=for-the-badge&logo=github&logoColor=white" alt="Profile" />
  </a>
  <a href="https://blxman-37fy.vercel.app/">
    <img src="https://img.shields.io/badge/Portfolio-blxman--37fy-0A66C2?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio" />
  </a>
</p>

---

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

---

## 📸 Web Interface Output

When running [`RoboticArm_Final.html`](RoboticArm_Final.html) in a modern web browser, the simulation renders an interactive 3D workspace with a dark industrial style containing the following components:

### 1. 3D WebGL Canvas Viewport
- **Size:** `900x680` pixels.
- **Scene Objects:**
  - **Robotic Arm:** Built hierarchically (Base column, Lower Arm, Upper Arm, Wrist, and two-finger Claw/Gripper).
  - **Platforms:** Left platform (Green, target drop site) and Right platform (Blue, initial pickup site).
  - **Interactable Object:** A 3D red cube resting on the platforms.
  - **Ground Grid:** Textured mesh providing depth reference.
- **Rendering & Shaders:** Implementing the **Blinn-Phong lighting model** with metallic material reflections, specular highlights, rim lighting, tone mapping, and gamma correction.

### 2. Control Dashboard Panel (Left Sidebar)
- **Joint Control Sliders:**
  - `Base Rotation (Q/E)`: `-180°` to `180°` range.
  - `Lower Arm (W/S)`: `-90°` to `90°` range.
  - `Upper Arm (↑/↓)`: `-150°` to `150°` range.
  - `Wrist (←/→)`: `-90°` to `90°` range.
  - `Gripper (Space)`: `0°` to `45°` claw opening angle.
- **Animation Customization Sliders:**
  - `Speed`: `0.1x` to `2.0x` adjustment.
  - `Object Size`: `0.5x` to `2.0x` scaling.
- **Color Customizers:** Color pickers for `Arm Color` and `Object Color`.
- **Action Buttons:** `START`, `STOP`, `RESET`, and `LOOP ON/OFF`.
- **Status Panel:** Displays current execution state (e.g. `Lifting object`, `Rotating to drop`), platform selection, and picking distance measurements.

### 3. Automated Pick & Place Sequence (8-State Loop)
Clicking `START` runs the robotic arm through an automated transition sequence:
1. **State 1:** Rotate base to align with the active pickup platform.
2. **State 2:** Reach down (adjust joint angles) towards the red cube.
3. **State 3:** Close gripper claw to grab the cube.
4. **State 4:** Lift the object up.
5. **State 5:** Rotate base and arm to align with the drop platform.
6. **State 6:** Lower the arm and cube down to the destination platform.
7. **State 7:** Open the gripper claw to release the cube.
8. **State 8:** Return the arm to the home/default pose.

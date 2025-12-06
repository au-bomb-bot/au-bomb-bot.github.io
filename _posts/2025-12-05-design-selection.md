---
layout: post
title: "Critical Design Review: Final Design Selection"
date: 2025-12-05
---

# Design Selection Overview

Following our Critical Design Review (CDR), the team has finalized the design approaches for the Explosive Atmosphere Chamber Robotic System. After analyzing various concepts through decision matrices, motion studies, and sponsor feedback, we have selected a unified system that prioritizes safety, range of motion, and modularity.

# Manipulator Positioning: Motor-Actuated Robotic Arm

We have selected the **Motor-Actuated Robotic Arm** as our primary manipulator. 
* **Mechanism:** A two-segment arm actuated by motors at the base, elbow, and wrist, mounted on a track system for side-to-side translation. This configuration ensures we meet the requirement for three degrees of freedom and covers the full 2x2x2 ft work area.
* **Material:** We chose **Aluminum 6061** for the frame. Our Finite Element Analysis (FEA) and motion studies showed that Aluminum 6061 offers the best balance of strength and weight (approx. 14.17 lbs for the arm), significantly reducing the torque required compared to steel alternatives.
* **Safety:** To mitigate ignition risks, motors will either be rated for MIL-STD-810H or housed in protective enclosures.

# Subsystem Manipulation and Tool Exchange

To interact with the various switches inside the chamber, we opted for a **Manual Tool Exchange System** with **Separate End-Effectors**.
* **Specialized Tools:** Instead of a single complex multi-tool, we will use distinct attachments designed for specific tasks:
    * **Toggle Switch Tool:** A simple mechanical linkage.
    * **Rotary Switch Tool:** A handle attachment for gripping and turning knobs.
    * **Stylus:** A conductive rubber tip for tactile membrane switches and touchscreens.
* **Exchange Mechanism:** A quick-release coupling at the end of the arm allows the operator to manually swap tools between tests. This approach was chosen for its mechanical simplicity, intrinsic safety, and low cost.

# Perception System

To ensure the operator has full situational awareness, we are implementing a **Combined Internal and External Camera System**.
* **External:** An **Aida UHD-100A** camera will be positioned outside the chamber's viewport. This provides a wide, safe view of the testing area and includes a built-in microphone for audio feedback.
* **Internal:** An **AMZ-HD41-3** explosion-proof camera will be mounted inside the chamber to provide alternative viewing angles that the external camera cannot reach.
* **Audio:** Audio monitoring will be handled via the external camera's built-in microphone, supplemented by an isolated external microphone if necessary.

# Controls and Electronics

Safety is paramount, so we have selected an **External Electronics** architecture.
* **Isolation:** All non-essential electronics (drivers, controllers, power supplies) will be housed outside the chamber. Only shielded motor cables and intrinsically safe sensor lines will penetrate the chamber walls.
* **Interface:** The operator will use a **Remote Control Console** (likely an industrial joystick or gamepad) connected to a custom Graphical User Interface (GUI).
* **Control Logic:** We are using a split-system architecture. A standard PC will handle the UI and video feeds, while a dedicated real-time motion controller (embedded board) will handle motor timing and safety checks.

# Conclusion

This finalized design allows us to meet all MIL-STD-810H safety requirements while providing the precise control needed to actuate delicate switches. The move to a motor-driven arm with external electronics strikes the best balance between functionality, safety, and budget. Our next steps involve finalizing the CAD drawings and beginning the prototyping phase.
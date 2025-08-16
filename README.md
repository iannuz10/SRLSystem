# VR Testbed for Collaborative Robotics in Unreal Engine 5

This project is a high-fidelity Virtual Reality simulation developed in Unreal Engine 5 for a Master's Thesis in Advanced Robotics. It serves as a modular testbed for the comparative analysis of human interaction with two distinct autonomous robotic assistants: a wearable Supernumerary Robotic Limb (SRL) and an external collaborative robot (cobot).

This work was conducted as part of the JEMARO (Japan-Europe Master in Advanced Robotics) program at École Centrale de Nantes (France) and Keio University (慶應義塾, Japan).

---

## 🚀 Project Overview

The core of this project is a complex, multi-step assembly task (building a stool) that a user performs in one of three experimental conditions:

-   **Solo**: Unassisted, using only their natural hands.
-   **SRL Collaboration**: Assisted by a pair of wearable, autonomous robotic arms.
-   **Cobot Collaboration**: Assisted by an external, autonomous cobot.

The primary goal was to create a robust platform to systematically investigate how different forms of robotic assistance affect task performance, user workload, and the subjective experience of embodiment and collaboration.

---

## ✨ Key Technical Features

### 1. Advanced VR Interaction System
-   **Physics-Based Grabbing**: Implemented from the ground up in C++ and Blueprints, the interaction system uses a physics-based approach where object manipulation is governed by constraints and forces, allowing for robust and intuitive handling of virtual tools and parts.
-   **Procedural Grasp Animation**: Features a procedural, physics-based grasp animation system that adapts to the shape of the object being held.
-   **Custom VR Pawn**: A custom pawn handles locomotion, hand tracking via OpenXR, and the dynamic attachment/detachment of the SRLs, ensuring seamless integration with the Meta Quest 3.

### 2. Modular Robotic Agents
-   **Finite State Machine (FSM)**: The autonomous behavior for both the SRL and the Cobot is governed by a complex, 15-state FSM designed in Blueprints. This FSM controls the "Reach-Grab-Bring" logic for part retrieval, ensuring identical autonomous behavior across both assistive conditions for a fair comparison.
-   **Interchangeable Partners**: The system is designed to be modular. The SRL and Cobot are implemented as separate, swappable components, demonstrating the testbed's flexibility for evaluating different robotic morphologies.

### 3. Proof-of-Concept Manual Control Modes
To showcase the platform's versatility as a research tool, several manual control strategies were also developed as a proof-of-concept:
-   **Mirroring**: A direct one-to-one kinematic mapping of the user's arm to the SRL.
-   **Polar Coordinate Control**: A non-isomorphic scheme mapping controller inputs to the SRL's position.
-   **Retargeting**: An advanced guided control mode based on the "virtual fixture" concept from the SyncArms system.

### 4. Comprehensive Data Logging
A custom data logging system captures a rich set of metrics for offline analysis.
-   **Objective Data**: Logs high-frequency 3D path data for all limbs, sub-task timestamps, error counts, and head orientation angles.
-   **Subjective Data Integration**: The system is designed to be used in conjunction with standard HRI questionnaires (NASA-TLX, UEQ-S, VEQ, Godspeed) to provide a complete picture of the user experience.

---

## 🛠️ How to Run the Project

-   **Engine Version**: This project was built using Unreal Engine 5.3.
-   **Hardware**: A Meta Quest 3 headset with Touch Plus controllers is required, connected to the PC via Quest Link.

**Setup:**
1.  Open the project in the Unreal Editor.
2.  Ensure the OpenXR plugin is enabled and configured for Meta Quest devices.
3.  The main level to run the simulation is `MainMenu`.

**Execution:**
1.  Start the simulation using the "VR Preview" mode in the editor.
2.  The user will be placed in the Main Menu space, where a virtual button menu is displayed.
3.  A Tutorial Level is available to familiarize the user with all interaction mechanics.
4.  After the tutorial, the user can relaunch the VR Preview, select one of the three experimental conditions, and proceed with the task.

---

## 💡 Key Skills Demonstrated

-   **Advanced Unreal Engine 5**: Architected and implemented complex game logic and interaction systems using a combination of C++ and Blueprints.
-   **VR Development**: Developed a high-fidelity, interactive VR experience from the ground up, targeting the Meta Quest 3 via the OpenXR standard.
-   **Robotics & AI**: Implemented a robust Finite State Machine for autonomous agent behavior and demonstrated a deep understanding of advanced HRI concepts like embodiment and shared control.
-   **Systematic Research & Design**: Designed and executed a complex system from initial concept to a fully functional research platform, capable of answering specific research questions in a methodologically sound way.

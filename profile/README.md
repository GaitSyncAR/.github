# GaitSyncAR: Augmented Reality Gait Rehabilitation Platform

**Project Demonstration Video:** [Watch Screencast Here](https://youtu.be/2aWwRzrZJKY)

## About the Project

**GaitSyncAR** is an immersive Augmented Reality (AR) rehabilitation platform designed to assist patients recovering from neurological and musculoskeletal conditions such as Parkinson's disease, stroke, and meningitis. Traditional physiotherapy can be labour-intensive and lacks continuous, quantitative feedback. GaitSyncAR modernises this process by pairing rhythmic visual, auditory, and haptic cueing in an AR environment with gait analysis derived from custom-built wearable ankle sensors. 

### Key Features
* **Zero-Latency Wearable Sensors:** Custom nRF52840-based hardware providing sub-millisecond clock synchronisation for accurate, real-time step tracking.
* **Immersive AR Cueing:** An optical see-through (OST) gesture-free interface that delivers rhythmic metronome cues (visual, auditory, and haptic) to stimulate neuroplasticity and guide walking pace.
* **Clinical Gait Analytics:** Calculates and archives critical stability metrics post-session, including:
  * Cadence (Steps per Minute)
  * Temporal Symmetry Ratio
  * Stride Time Variability (CV%)
  * Inter-limb Temporal Phase Offset
* **Session Archival & Scoring:** Automatically synthesises complex biometric data into a digestible 10-point "Stability Score" for easy review by patients and clinicians.

---

## Project Repository Structure

Because this project spans custom hardware, embedded firmware, and an AR software environment, the source code and assets are divided into dedicated repositories and directories. 

### 1. Unity Orchestrator (C#)
* **Repository:** [GaitSyncAR-VG](https://github.com/GaitSyncAR/GaitSyncAR-VG)
* **Description:** Contains the core Unity 3D project. This application manages the AR environment, processes incoming Bluetooth Low Energy (BLE) sensor data, handles the UI/UX, and calculates the derived clinical metrics.

### 2. Embedded Firmware (C / Zephyr RTOS)
* **Repository:** [GaitSyncAR_NRF_Sense](https://github.com/GaitSyncAR/GaitSyncAR_NRF_Sense)
* **Description:** Contains the Zephyr RTOS source code for the primary and secondary nRF52840 sensor nodes. It handles the raw IMU data capture, real-time clock synchronisation, and BLE transmission.

### 3. Hardware & 3D Design Files (CAD)
* **Link:** [Download STL & CAD Files (Google Drive)](https://drive.google.com/file/d/12ckUizZyPBIqEu3kfGE-ti41WXDw3-view?usp=sharing)
* **Description:** Includes the `.stl` files and original CAD project files used for additive manufacturing (3D printing) the custom wearable sensor housings.

### 4. Dissertation & A0 Poster
**Repository:** [GaitSyncAR Root (.github)](https://github.com/GaitSyncAR/.github)
**Description:** Contains the final written dissertation report and the A0 academic presentation poster associated with the project.
---

## Compilation, Deployment, and Running

*(Note: Detailed, step-by-step build instructions for the specific software stacks are located in the `README.md` files of their respective repositories. Below is the high-level deployment overview).*

### Deploying the Sensor Firmware
1. Clone the `GaitSyncAR_NRF_Sense` repository.
2. Ensure you have the **nRF Connect SDK** and **Zephyr toolchain** installed.
3. Flash the compiled firmware onto the Seeed Studio XIAO nRF52840 microcontrollers via USB.

### Deploying the AR Unity Application
1. Clone the `GaitSyncAR-VG` repository.
2. Open the project in **Unity** (ensure the AR Foundation and relevant target build modules are installed).
3. Build the project for your target AR device.
4. Launch the application. Ensure the ankle sensors are powered on; the Unity application will automatically establish a BLE handshake to begin streaming gait data.

## Project Poster
<img width="1175" height="1660" alt="{FAD919BA-2C04-42B4-A543-2E0C09E46705}" src="https://github.com/user-attachments/assets/c81ba19c-7265-4ced-b1ad-75c3a68084f0" />

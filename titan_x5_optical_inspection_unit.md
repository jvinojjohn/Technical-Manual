# SERVICE MANUAL: TITAN-X5 OPTICAL INSPECTION UNIT

| Metadata | Details |
| :--- | :--- |
| **Document ID** | TM-TITAN-X5-002 |
| **Revision** | 1.0 |
| **Date** | December 14, 2025 |
| **Audience** | Certified Field Service Engineers (FSE) |

---
## DOCUMENT CONTROL


| Revision | Date | ECO # | Author | Description of Changes |
| :--- | :--- | :--- | :--- | :--- |
| **1.0** | 14-Dec-2025 | ECO-2601 | Vinoj John | Initial Release |

---

## TABLE OF CONTENTS

* [1. SAFETY & COMPLIANCE](#1-safety--compliance)
    * [1.1 General Safety](#11-general-safety)
    * [1.2 Lockout/Tagout (LOTO) Requirements](#12-lockouttagout-loto-requirements)
    * [1.3 Laser Safety](#13-laser-safety)
* [2. SYSTEM DESCRIPTION & THEORY OF OPERATION](#2-system-description--theory-of-operation)
    * [2.1 Functional Overview](#21-functional-overview)
    * [2.2 Image Acquisition Subsystem](#22-image-acquisition-subsystem)
    * [2.3 Motion Control Architecture](#23-motion-control-architecture)
* [3. PREVENTIVE MAINTENANCE (PM) PROCEDURES](#3-preventive-maintenance-pm-procedures)
    * [3.1 PM Interval Schedule](#31-pm-interval-schedule)
    * [3.2 Procedure: PM-02 Linear Guide Lubrication](#32-procedure-pm-02-linear-guide-lubrication)
* [4. DIAGNOSTICS & TROUBLESHOOTING](#4-diagnostics--troubleshooting)
    * [4.1 Error Code Logic](#41-error-code-logic)
    * [4.2 Advanced Troubleshooting: Vision Acquisition Failure](#42-advanced-troubleshooting-vision-acquisition-failure)
* [5. DECOMMISSIONING & DISPOSAL](#5-decommissioning--disposal)
    * [5.1 Hazardous Materials Removal](#51-hazardous-materials-removal)
    * [5.2 Recycling](#52-recycling)
* [6. APPENDIX A: ABBREVIATIONS & ACRONYMS](#6-appendix-a-abbreviations--acronyms)
---

## 1. SAFETY & COMPLIANCE

### 1.1 General Safety
Only qualified personnel who have completed the **Level 3 High-Voltage Training** are authorized to perform maintenance on the Titan-X5.

### 1.2 Lockout/Tagout (LOTO) Requirements
Before removing any enclosure panels, you must isolate the system from all energy sources.

> <img width="176" height="158" alt="image" src="https://github.com/user-attachments/assets/72886655-6373-45d7-a0a3-cc1a10573e4a" />

> **DANGER:**
> **HIGH VOLTAGE HAZARD (480V AC)**
>
> Failure to follow LOTO procedures will result in **death or serious injury**.
> 1. Turn the Main Disconnect Switch (SW-01) to the **OFF** position.
> 2. Apply a padlock and tag to the switch.
> 3. Measure voltage at Terminal Block TB-1 to verify 0V potential.

### 1.3 Laser Safety
The Titan-X5 utilizes a Class 3B Laser for surface topology scanning.

> <img width="182" height="155" alt="image" src="https://github.com/user-attachments/assets/c7ee4067-2e2a-4f21-988c-56c6c9563ce4" />

> **WARNING:**
> **LASER RADIATION**
>
> **Avoid direct eye exposure.** Do not stare into the beam or view directly with optical instruments.
> * **Wavelength:** 650 nm
> * **Max Output:** 50 mW
> * Always wear **OD 4+** protective eyewear when the interlock bypass key is active.

---

## 2. SYSTEM DESCRIPTION & THEORY OF OPERATION

### 2.1 Functional Overview
The Titan-X5 is an Automated Optical Inspection (AOI) system designed for semiconductor wafer defect detection. It combines high-resolution CCD imaging with laser triangulation to identify defects down to 5µm.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/60bd0b1b-1e00-4d33-9f62-07790276cba2" />

### 2.2 Image Acquisition Subsystem
The core imaging logic is controlled by the **Vision Processing Unit (VPU)**.

1.  **Triggering:** The PLC sends a `TRIG_REQ` signal to the VPU when the wafer is in position.
2.  **Strobe Lighting:** The VPU activates the LED Ring Light (Strobe Mode) for 50ms.
3.  **Capture:** Simultaneously, the CCD camera captures the frame and transfers raw data via Camera Link to the Frame Grabber.

### 2.3 Motion Control Architecture
The X-Y stage is driven by linear motors with linear encoder feedback.
* **Controller:** Galil DMC-4000
* **Feedback Resolution:** 0.1µm
* **Communication:** EtherCAT bus

---

## 3. PREVENTIVE MAINTENANCE (PM) PROCEDURES

### 3.1 PM Interval Schedule

| Frequency | Procedure ID | Description | Estimated Time |
| :--- | :--- | :--- | :--- |
| **Monthly** | PM-01 | Clean Optical Lens & Filters | 15 min |
| **Quarterly** | PM-02 | Lubricate Linear Guides | 30 min |
| **Annually** | PM-05 | Z-Axis Calibration & Lead Screw Inspection | 2 hours |

### 3.2 Procedure: PM-02 Linear Guide Lubrication

**Prerequisites:**
* System is in **MAINTENANCE MODE**. Refer to *Operation Manual, Section 5.1 for activation steps*.
* Lint-free cloths and Isopropyl Alcohol (IPA).
* Grease Gun with Lithium-based grease (Part # LUB-99).

**Steps:**

1.  Open the front access door to access the XY stage.

2.  Wipe the X-axis and Y-axis guide rails with a lint-free cloth dampened with IPA.
    * *Caution:* Do not touch the linear encoder scale (gold strip). Acid from fingerprints can degrade the scale.
<img width="344" height="260" alt="image" src="https://github.com/user-attachments/assets/f6deb584-6225-41a5-bdea-743e8d5e3e82" />

3.  Locate the grease nipple on the four runner blocks (2 per axis).  
4. Pump the grease gun twice (approx. 0.5cc) into each nipple.
<img width="337" height="266" alt="image" src="https://github.com/user-attachments/assets/5cac83ed-1e17-4090-8da5-c036d8c7818d" />
<img width="334" height="251" alt="image" src="https://github.com/user-attachments/assets/e821aa9f-c7a1-4813-9c7a-14a6dc4cd7dc" />


5.  Manually push the stage slowly from end-to-end three times to distribute the grease evenly.
<img width="340" height="255" alt="image" src="https://github.com/user-attachments/assets/7af713c7-999c-49ee-aaa3-1a205d86f2c6" />

6.  Check for any binding or excessive friction.

<img width="338" height="250" alt="image" src="https://github.com/user-attachments/assets/9e5fc397-9d01-4a3a-a59b-61cf4b2f7baf" />


---

## 4. DIAGNOSTICS & TROUBLESHOOTING

### 4.1 Error Code Logic
The system reports errors via the HMI Control Panel. Use the table below to isolate faults.

| Error Code | Fault Description | Logic / Trigger Condition | Corrective Action |
| :--- | :--- | :--- | :--- |
| **E-101** | **E-Stop Active** | Safety Relay `K1` is de-energized (Open). | 1. Check physical E-Stop buttons.<br>2. Verify 24V DC at Relay `K1`. |
| **E-204** | **Motion Limit Trip** | Axis position > Soft Limit variable. | 1. Reset drive.<br>2. Manually jog axis away from end-stop.<br>3. Re-home system. |
| **E-305** | **Vision Timeout** | VPU did not return `IMG_READY` < 500ms. | 1. Check Camera Link cable seating.<br>2. Reboot VPU.<br>3. See Flowchart 4.2. |

### 4.2 Advanced Troubleshooting: Vision Acquisition Failure

**Symptom:** System triggers, strobe flashes, but no image appears on the monitor.

**Diagnostic Flow:**

1.  **Check Frame Grabber Status:**
    * Open Device Manager in the OS. Is the `Matrox Solios` card listed?
    * **IF NO:** Reseat the PCI card. Replace if necessary.
    * **IF YES:** Proceed to Step 2.

2.  **Verify Trigger Signal:**
    * Connect an oscilloscope to **TP-4** (Trigger In) on the VPU breakout board.
    * Command a manual trigger.
    * **Observation:** Do you see a 5V TTL rising edge?

    <img width="325" height="299" alt="image" src="https://github.com/user-attachments/assets/979c8390-6589-4aeb-a1e9-25810f4796aa" />

    * **IF NO:** Fault lies in the PLC output module or wiring harness `W-202`. (See Schematic DWG-900-E).
    * **IF YES:** The VPU is receiving the command but failing to capture. Proceed to Step 3.

3.  **Camera Link Integrity Test:**
    * Swap the Camera Link cable with a known good test cable.
    *Note:* Cables longer than 5m often experience signal degradation if not ferrite-shielded.

---

## 5. DECOMMISSIONING & DISPOSAL

At the end of the product's service life, the Titan-X5 must be disposed of in accordance with **Directive 2012/19/EU (WEEE)**.

### 5.1 Hazardous Materials Removal

> [!WARNING]
> **CHEMICAL HAZARD**
> The internal backup battery and capacitors contain materials that may be harmful if leaked.

1.  **Backup Battery:**
    * Locate the CR2032 Lithium coin cell on the Motherboard (PCBA-01).
    * Remove and recycle at a designated battery collection point.
2.  **Capacitors:**
    * The Motor Drive (VFD) contains electrolytic capacitors.
    * Ensure they are fully discharged before removal. Treat as industrial electronic waste.
3.  **Cooling Fluids:**
    * If the optional Chiller Unit is installed, drain the Glycol coolant into a sealed container. Do not flush down the drain.

### 5.2 Recycling
* **Steel/Aluminum Chassis:** 100% Recyclable. Remove all plastic covers before scrapping.
* **Cabling:** Strip copper wiring for recycling.
---

## 6. APPENDIX A: ABBREVIATIONS & ACRONYMS

The following abbreviations and acronyms are used throughout this manual.

| Abbreviation | Definition | Context / Notes |
| :--- | :--- | :--- |
| **AC** | Alternating Current | Power supply specification. |
| **AOI** | Automated Optical Inspection | The system type; uses optics to inspect parts. |
| **CCD** | Charge-Coupled Device | The imaging sensor technology used in the camera. |
| **DC** | Direct Current | Low voltage power (e.g., 24V control signals). |
| **FSE** | Field Service Engineer | Qualified personnel authorized to service the unit. |
| **HMI** | Human-Machine Interface | The touch panel used to control the system. |
| **IPA** | Isopropyl Alcohol | Cleaning solvent used for optics and guide rails. |
| **LOTO** | Lockout/Tagout | Safety procedure to ensure energy isolation. |
| **OD** | Optical Density | Rating for laser safety eyewear protection level. |
| **PCI** | Peripheral Component Interconnect | The internal expansion card interface (Frame Grabber). |
| **PLC** | Programmable Logic Controller | The industrial computer controlling logic signals. |
| **PM** | Preventive Maintenance | Scheduled maintenance tasks to prevent failure. |
| **TTL** | Transistor-Transistor Logic | 5V digital signal standard (used for Triggering). |
| **VPU** | Vision Processing Unit | The subsystem responsible for image processing. |

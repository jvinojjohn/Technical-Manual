u# INSTALLATION MANUAL: VORTEX-900 INDUSTRIAL POWER UNIT

**Document ID:** IM-VTX900-04 | **Rev:** 2.1 | **Date:** 12-Dec-2025
**Applicable Models:** VTX-900-A (480V), VTX-900-E (400V)

---

## 1. PRE-INSTALLATION SAFETY

**Danger Level:** **CRITICAL**
Only certified electricians with **NFPA 70E (Arc Flash)** training are authorized to install this unit.

> <img width="162" height="140" alt="image" src="https://github.com/user-attachments/assets/29ae9110-9403-476a-b85c-b3356bb9bc91" />

> **ARC FLASH & SHOCK HAZARD**
> * **Voltage:** 480V AC, 3-Phase.
> * **Incident Energy:** > 40 cal/cm².
> * Ensure upstream feeder breaker is locked out and tagged out (**LOTO**).

---

## 2. SITE PREPARATION & REQUIREMENTS

### 2.1 Environmental Specifications
Ensure the installation location meets the following criteria before uncrating the unit:

* **Ambient Temperature:** -10°C to +40°C (14°F to 104°F).
* **Relative Humidity:** < 95% Non-condensing.
* **Floor Loading:** Concrete floor must support a point load of **1,200 kg/m²**.

### 2.2 Foundation Mounting Pattern
The VTX-900 requires **Seismic Zone 4** anchoring.

1.  Mark the four anchor points on the concrete pad according to **Figure 2.1**.
2.  Drill holes using a **16mm masonry bit** to a depth of **100mm**.

*Figure 2.1: Seismic Anchor Bolt Pattern (Top View)*  
<img width="654" height="343" alt="image" src="https://github.com/user-attachments/assets/297cba5f-d6a4-439f-95ee-115a8c54f880" />


---

## 3. MECHANICAL INSTALLATION

### 3.1 Uncrating and Positioning
**Tools Required:** Pallet Jack (2-ton capacity), Spirit Level, 19mm Socket Wrench.

1.  Remove the outer plywood crating.

    <img width="341" height="170" alt="image" src="https://github.com/user-attachments/assets/a7f92518-b021-4e8d-a4d5-450575a9353d" />

2.  Inspect the **Shock Watch** indicator on the chassis.  
  If red, halt the installation and contact Logistics.

    <img width="344" height="172" alt="image" src="https://github.com/user-attachments/assets/51ddc0b4-cdfc-4acb-926b-221f929a965e" />

3.   Using the pallet jack, position the unit over the drilled anchor holes.  
    <img width="334" height="168" alt="image" src="https://github.com/user-attachments/assets/0245868e-2c98-4c42-8206-c82e14ba298b" />

4.  Insert the four **M16 x 100mm expansion anchors**.

5.  Level the unit using the adjustable feet until the spirit level indicates < 0.5° tilt in both X and Y axes.
    <img width="337" height="169" alt="image" src="https://github.com/user-attachments/assets/442bfb7c-bc35-4d32-948e-bb1081400aed" />

6.  Tighten the anchor nuts. **Torque to 80 Nm (59 ft-lb).**

---

## 4. ELECTRICAL CONNECTIONS

### 4.1 Input Power Cabling (Line Side)
**Cable Spec:** 4/0 AWG Copper, 90°C rated insulation.

1.  Remove the **Safety Shield** (Polycarbonate) from the input busbars.  
    <img width="332" height="514" alt="image" src="https://github.com/user-attachments/assets/26dd353c-ea33-4a7f-a0cf-350c0ff8ee51" />

2.  Remove **25 mm** of insulation from the input cables (L1, L2, L3, Ground).  
    <img width="329" height="261" alt="image" src="https://github.com/user-attachments/assets/917c71ca-274e-481a-8e55-bc91689e9f48" />

3.  Connect the cables to the mechanical lugs on the Input Breaker (CB-01).
    * **Note:** Make sure that the cable bend radius is more than 8 times the cable diameter. This prevents stress on the lugs.   

*Figure 4.1: Input Termination Block*  
    <img width="332" height="268" alt="image" src="https://github.com/user-attachments/assets/e9c2bfe9-de0f-4e46-a485-809f4f3b89cb" />
    
4.  Tighten the lug set screws. Refer to Table 4.1 for the torque values.

*Table 4.1: Input Termination Block*

| Wire Size (AWG/kcmil) | Socket Size (Hex) | Torque (Nm) | Torque (in-lb) |
| :--- | :--- | :--- | :--- |
| \#4 - 2/0 | 6 mm | 15 Nm | 132 in-lb |
| 3/0 - 4/0 | 8 mm | 22 Nm | 194 in-lb |
| 250 - 350 | 10 mm | 30 Nm | 265 in-lb |

5.  Install the Safety Shield again. 
>WARNING!: Do not supply power to the unit if the shield is not in position.

  <img width="326" height="250" alt="image" src="https://github.com/user-attachments/assets/fe4d2120-ea3e-4c8d-9bbe-42f8bba231c5" />

### 4.2 Control & Signal Wiring (Low Voltage)
The VTX-900 communicates via **Modbus TCP/IP** for remote monitoring.

1.  Route the CAT6 Ethernet cable through the bottom gland plate (Entry B).
2.  Connect to port **ETH-0** on the internal PLC.
3.  **Interlock Loop:**
    * Connect the external Emergency Stop circuit to Terminal Block **TB-2 (Pins 1 & 2)**.
    * *Note:* If no external E-Stop is used, install a jumper wire between Pins 1 & 2.

    <img width="650" height="313" alt="image" src="https://github.com/user-attachments/assets/03165f36-029d-40d5-baac-75516157ea83" />

---

## 5. COMMISSIONING & STARTUP

### 5.1 Insulation Resistance Test (Megger)
Before applying power, verify insulation integrity.

1.  Disconnect neutral-to-ground bond (if applicable).
2.  Apply **1000V DC** between Phase and Ground.
3.  **Pass Criteria:** Resistance must be > 100 MΩ.

### 5.2 Phase Rotation Check
1.  Close the upstream feeder breaker (Power ON).
2.  Verify the **Phase Sequence Monitor (Relay K-4)** LED is **GREEN**.
    * **Green:** Sequence is ABC (Clockwise). Proceed.
    * **Red:** Sequence is CBA (Counter-Clockwise). **STOP.** Isolate power and swap L1 and L2 cables.

### 5.3 Voltage Verification
Measure voltage at the Load Side of the main breaker:
* **L1 - L2:** 480V ±10%
* **L2 - L3:** 480V ±10%
* **L3 - L1:** 480V ±10%

---

## 6. FINAL HANDOVER
1.  Complete the **Commissioning Checklist (Form C-900)**.
2.  Apply the "Service Contact" label to the front door.
3.  Hand over keys to the Facility Manager.

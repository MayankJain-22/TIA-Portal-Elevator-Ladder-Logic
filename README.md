# 🏢 PLC Elevator System — Siemens TIA Portal V17

A **4-floor elevator control system** programmed using **Ladder Logic** in **Siemens TIA Portal V17**, developed as part of the PLC & HMI subject under the B.Tech Robotics and Automation program at Bharati Vidyapeeth (Deemed to be University), Pune.

The system automates elevator movement, floor selection, door operation, and safety interlocks using a Programmable Logic Controller (PLC), demonstrating real-world industrial automation concepts.

---

## 📹 Demo Video

[![Demo Video](https://img.shields.io/badge/YouTube-Demo%20Video-red?logo=youtube)](YOUR_YOUTUBE_LINK_HERE)

> The demo video shows the full simulation running in TIA Portal — floor calls, motor direction, door operation, and emergency stop in action.

---

## 📸 Screenshots

> Add screenshots of your TIA Portal ladder logic rungs and simulation view to the `Images/` folder.

| Ladder Logic | Simulation View |
|:------------:|:---------------:|
| ![Ladder](Images/ladder_diagram.png) | ![Simulation](Images/simulation.png) |

---

## 📌 Overview

This project implements a complete PLC-based elevator controller with:

- **Floor call handling** — buttons on each floor and inside the cabin send requests to the PLC
- **Direction logic** — PLC determines up/down movement based on current position vs requested floor
- **Limit switch feedback** — precise stopping at each floor using position sensors
- **Automatic door control** — doors open on arrival, hold for 3 seconds, then close automatically
- **Safety interlocks** — elevator cannot move while doors are open; overload protection halts operation
- **Emergency stop** — immediate safe halt from any state
- **Priority logic** — handles multiple floor requests in sequence

---

## ✨ Features

- 4-floor elevator simulation in TIA Portal V17
- Ladder Diagram (LD) programming — IEC 61131-3 standard
- Upward and downward motor direction control with mutual interlock
- Limit switch-based precise floor detection
- Timer-controlled automatic door open/close (3 second hold)
- Door interlock — motor blocked while door is open
- Overload protection sensor input
- Emergency stop with immediate motor cut-off
- Floor indicator lamps for each level
- System ready / active status lamp
- Alarm buzzer output for emergency and overload conditions

---

## 🛠️ Technologies Used

### Software

| Tool | Version | Purpose |
|------|---------|---------|
| Siemens TIA Portal | V17 | PLC programming and project environment |
| PLCSIM | V17 | Software simulation — no physical PLC needed |

### PLC Programming

- **Language:** Ladder Diagram (LD) — IEC 61131-3
- **Target PLC:** Siemens S7-1200 / S7-1500 (simulated via PLCSIM)

### Hardware Components (Physical / Simulated)

| Component | Purpose |
|-----------|---------|
| PLC (S7-1200/1500) | Core controller |
| Floor Call Push Buttons ×4 | User floor requests |
| Limit Switches ×4 | Floor position feedback |
| Door Open / Close Sensors | Confirm door state |
| DC Motor / Contactor | Drives elevator up or down |
| Door Actuator | Opens and closes cabin doors |
| Floor Indicator Lamps ×4 | Visual floor display |
| Overload Sensor | Weight protection input |
| Emergency Stop Button | Immediate system halt |
| Alarm Buzzer | Audio fault alert |

---

## 🏗️ System Architecture

```
Floor Call Buttons (×4)
Limit Switches (×4)          ──→   PLC Digital Inputs
Door Sensors
Emergency Stop / Overload

              ↓
      Siemens S7-1200
      Ladder Logic (OB1)
      TIA Portal V17
              ↓

Motor Up / Motor Down        ──→   PLC Digital Outputs
Door Open / Door Close
Floor Indicator Lamps (×4)
Alarm Buzzer / System Ready
```

---

## 🔌 I/O Tag Reference

### Digital Inputs

| Tag | Address | Description |
|-----|---------|-------------|
| Start_PB | %I0.0 | System start push button |
| Stop_PB | %I0.1 | System stop push button |
| Emergency_Stop | %I0.2 | Emergency halt (NC contact) |
| Floor1_Call | %I0.3 | Floor 1 call button |
| Floor2_Call | %I0.4 | Floor 2 call button |
| Floor3_Call | %I0.5 | Floor 3 call button |
| Floor4_Call | %I0.6 | Floor 4 call button |
| Floor1_Limit | %I1.0 | Elevator at Floor 1 |
| Floor2_Limit | %I1.1 | Elevator at Floor 2 |
| Floor3_Limit | %I1.2 | Elevator at Floor 3 |
| Floor4_Limit | %I1.3 | Elevator at Floor 4 |
| Door_Open_Sensor | %I1.4 | Door fully open confirmation |
| Door_Close_Sensor | %I1.5 | Door fully closed confirmation |
| Overload_Sensor | %I1.6 | Weight overload protection |

### Digital Outputs

| Tag | Address | Description |
|-----|---------|-------------|
| Motor_Up | %Q0.0 | Elevator motor — upward |
| Motor_Down | %Q0.1 | Elevator motor — downward |
| Door_Open | %Q0.2 | Door open actuator |
| Door_Close | %Q0.3 | Door close actuator |
| Floor1_Indicator | %Q0.4 | Floor 1 lamp |
| Floor2_Indicator | %Q0.5 | Floor 2 lamp |
| Floor3_Indicator | %Q0.6 | Floor 3 lamp |
| Floor4_Indicator | %Q0.7 | Floor 4 lamp |
| Alarm_Buzzer | %Q1.0 | Emergency / overload alarm |
| System_Ready | %Q1.1 | System active indicator |

### Timers

| Tag | Type | Preset | Description |
|-----|------|--------|-------------|
| Door_Open_Timer | TON | 3s | Auto-close delay after door opens |
| Motor_Delay_Timer | TON | 0.5s | Delay before motor starts after door closes |

> Full tag reference also available in [`Docs/IO_Tag_Reference.md`](Docs/IO_Tag_Reference.md)

---

## 📁 Repository Structure

```
PLC-Elevator-System/
│
├── README.md
├── .gitignore
│
├── TIA_Portal_Project/
│   ├── Elevator_System.prx          ← Main TIA Portal project (open this)
│   └── Midway_Checkpoint.prx        ← Intermediate saved version
│
├── Ladder_Diagram/
│   └── (add exported ladder diagram screenshots or PDF here)
│
├── Images/
│   └── (add TIA Portal screenshots here)
│
└── Docs/
    └── IO_Tag_Reference.md          ← Complete I/O tag and address table
```

---

## ⚙️ How to Open the Project

### Requirements

- **Siemens TIA Portal V17** or later (student/trial license available from Siemens)
- **PLCSIM V17** for software simulation (no physical PLC required)

> ⚠️ `.prx` files are proprietary Siemens TIA Portal archives. They cannot be opened with any other software. If you don't have TIA Portal, watch the [demo video](YOUR_YOUTUBE_LINK_HERE) to see the full simulation.

### Steps

1. Open **Siemens TIA Portal V17**
2. Click **"Open existing project"**
3. Navigate to `TIA_Portal_Project/`
4. Select `Elevator_System.prx` → click **Open**
5. In the Project tree expand **PLC_1 → Program blocks → Main [OB1]**
6. Double-click to view the ladder logic networks
7. To run simulation: **Online → Start simulation** (PLCSIM must be installed)

---

## 🔄 System Workflow

```
Start button pressed
        ↓
System initialises — all outputs reset to safe state
        ↓
Floor call button pressed
        ↓
PLC compares requested floor vs current floor
        ↓
    Door closed?
   YES ↓        ↑ NO — wait
Motor activates (Up or Down)
        ↓
Limit switch at target floor triggers
        ↓
Motor stops
        ↓
Door opens → Door_Open_Timer (3s) starts
        ↓
Timer expires → Door closes automatically
        ↓
Ready for next call
        ↓
(Emergency Stop at any point)
→ Motor OFF immediately
→ Alarm Buzzer ON
→ System halted until reset
```

---

## 🔒 Safety Logic

| Feature | How It Works |
|---------|-------------|
| Door Interlock | Motor rungs require Door_Close_Sensor (NC) — door open breaks the circuit |
| Emergency Stop | Normally-closed contact in series with all motor outputs |
| Overload Protection | Overload_Sensor disables motors and activates alarm buzzer |
| Direction Interlock | Motor_Up and Motor_Down are mutually exclusive — cannot energise simultaneously |
| Limit Switch Stop | Floor limit switch de-energises motor rung and triggers door open sequence |

---

## 📚 Learning Outcomes

- PLC programming with Ladder Diagram (IEC 61131-3)
- Siemens TIA Portal V17 project structure and tag configuration
- Digital I/O mapping and address assignment
- TON timer usage for timed door sequencing
- Safety interlock design principles
- Motor direction control with mutual interlocking
- Limit switch and sensor feedback in PLC logic
- Emergency stop and fault handling

---

## 🚀 Future Improvements

- [ ] HMI screen design in TIA Portal for live floor visualization
- [ ] Priority queue for multiple simultaneous floor calls
- [ ] Inside cabin call buttons (separate from floor buttons)
- [ ] Door obstruction detection with re-open logic
- [ ] Expand to 6+ floor operation
- [ ] Energy-saving idle/sleep mode
- [ ] Deploy on physical S7-1200 hardware

---

## 👥 Team

| Name | PRN | Roll No. |
|------|-----|----------|
| Mayank Jain | 2314110615 | 35 |
| Ayush Singh | 2314110597 | 19 |
| Vaishnavi N Yerunkar | 2314110600 | 21 |
| Syed Sami | 2314110618 | 38 |

**Guide:** Prof. Mahavir Beldar
**Department:** Robotics and Automation
**Institute:** Bharati Vidyapeeth (Deemed to be University), College of Engineering, Pune
**Academic Year:** 2025–26

---

## 📄 License

This project is shared for educational and learning purposes.

# PLC I/O Tag Reference — Elevator System

> This document lists the suggested I/O tag mapping used in the TIA Portal ladder logic program.
> Open `Elevator_System.prx` in Siemens TIA Portal V17 or later to view exact addresses.

---

## Digital Inputs

| Tag Name | Address | Description |
|----------|---------|-------------|
| Start_PB | %I0.0 | Start push button — activates the system |
| Stop_PB | %I0.1 | Stop push button — halts system safely |
| Emergency_Stop | %I0.2 | Emergency stop — immediate halt |
| Floor1_Call | %I0.3 | Floor 1 call button |
| Floor2_Call | %I0.4 | Floor 2 call button |
| Floor3_Call | %I0.5 | Floor 3 call button |
| Floor4_Call | %I0.6 | Floor 4 call button |
| Floor1_Limit | %I1.0 | Limit switch — elevator at Floor 1 |
| Floor2_Limit | %I1.1 | Limit switch — elevator at Floor 2 |
| Floor3_Limit | %I1.2 | Limit switch — elevator at Floor 3 |
| Floor4_Limit | %I1.3 | Limit switch — elevator at Floor 4 |
| Door_Open_Sensor | %I1.4 | Door fully open confirmation sensor |
| Door_Close_Sensor | %I1.5 | Door fully closed confirmation sensor |
| Overload_Sensor | %I1.6 | Weight overload protection sensor |

---

## Digital Outputs

| Tag Name | Address | Description |
|----------|---------|-------------|
| Motor_Up | %Q0.0 | Elevator motor — upward direction |
| Motor_Down | %Q0.1 | Elevator motor — downward direction |
| Door_Open | %Q0.2 | Door open actuator |
| Door_Close | %Q0.3 | Door close actuator |
| Floor1_Indicator | %Q0.4 | Floor 1 position indicator lamp |
| Floor2_Indicator | %Q0.5 | Floor 2 position indicator lamp |
| Floor3_Indicator | %Q0.6 | Floor 3 position indicator lamp |
| Floor4_Indicator | %Q0.7 | Floor 4 position indicator lamp |
| Alarm_Buzzer | %Q1.0 | Emergency / overload alarm output |
| System_Ready | %Q1.1 | System active indicator lamp |

---

## Internal Markers / Memory Bits

| Tag Name | Address | Description |
|----------|---------|-------------|
| Direction_Up | %M0.0 | Internal flag — elevator moving up |
| Direction_Down | %M0.1 | Internal flag — elevator moving down |
| Door_Interlock | %M0.2 | Prevents motion when door is open |
| System_Active | %M0.3 | System running flag |

---

## Timers

| Tag Name | Type | Preset | Description |
|----------|------|--------|-------------|
| Door_Open_Timer | TON | 3s | Keeps door open for 3 seconds before auto-close |
| Motor_Delay_Timer | TON | 0.5s | Delay before motor starts after door closes |

---

> ⚠️ These addresses are based on the report and simulation logic.
> Verify against the actual TIA Portal project tags in `Elevator_System.prx`.

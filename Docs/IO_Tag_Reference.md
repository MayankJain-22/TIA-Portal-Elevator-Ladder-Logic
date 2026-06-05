# PLC I/O Tag Reference — Elevator System
# TIA Portal V20 — Extracted from project tag table

---

## Digital Outputs (Q)

| Tag Name | Address | Data Type | Description |
|----------|---------|-----------|-------------|
| first floor indication | %Q0.0 | Bool | First floor position indicator lamp |
| second floor indication | %Q0.1 | Bool | Second floor position indicator lamp |
| ground floor indication | %Q0.2 | Bool | Ground floor position indicator lamp |
| motor up | %Q0.3 | Bool | Elevator motor — upward direction |
| motor down | %Q0.4 | Bool | Elevator motor — downward direction |
| door open | %Q0.5 | Bool | Door open actuator output |
| door close | %Q0.6 | Bool | Door close actuator output |

---

## Memory Bits (M) — Internal Flags

| Tag Name | Address | Data Type | Description |
|----------|---------|-----------|-------------|
| first floor sw | %M0.0 | Bool | Elevator at first floor — position flag |
| second floor sw | %M0.1 | Bool | Elevator at second floor — position flag |
| ground floor sw | %M0.2 | Bool | Elevator at ground floor — position flag |
| second to ground | %M0.3 | Bool | Direction flag — travelling second floor → ground |
| ground to second | %M0.4 | Bool | Direction flag — travelling ground → second floor |
| door button | %M0.5 | Bool | Door open request / door interlock bit |

---

## Timers

| Tag Name | Type | Description |
|----------|------|-------------|
| upward lift timer | TON | Controls upward motor run duration |
| downward lift timer | TON | Controls downward motor run duration |
| close timer | TON | Delay before door close activates |
| open timer | TON | Duration door remains open |
| second floor to ... | TON | Transition timer for second floor travel |
| ground to second ... | TON | Transition timer for ground to second travel |

---

> Tags verified from TIA Portal Watch Table screenshot captured during live simulation.
> Open `TIA_Portal_Project/Elevator_System.prx` in TIA Portal V20 for full tag details.

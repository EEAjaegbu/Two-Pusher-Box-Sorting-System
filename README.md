# Two Pusher Box Sorting System

**Clean PLC ladder logic for dual-pusher conveyor sorting in CODESYS + Factory I/O**

**Author:** Ebuka Emmanuel Ajaegbu  
**Date:** 30 April 2026  
**Framework:** RAPID Engineer Framework v2.0

### Objective
Reliable box sorting system that classifies boxes (Small/Medium/Large) using three sensors and diverts them with two pneumatic pushers, including retract feedback, timeout faults, and counters.

### Key Features
- Rising-edge classification with R_TRIG (S_Low, S_Mid, S_High)
- One-shot memory flags (Small_Flag, Medium_Flag)
- Position-triggered pushers (S_P1, S_P2)
- Exact 1 s pusher actuation using TON timers
- Retract feedback monitoring with 3 s timeout faults
- Start button debounce with TON + TP (5 s / 10 s) and Siren/Alarm
- Counters for Small, Medium, and Large boxes
- Clean ResetPB for faults and counters
- Short, maintainable ladder logic

### Technologies
- **PLC:** CODESYS (Ladder Diagram)
- **Simulator:** Factory I/O
- **Approach:** RAPID Engineer Framework v2.0

### How It Works
1. StartPB → 5 s TON + 10 s TP for debounce → conveyor runs and RunLatch sets.
2. Box passes classification sensors → R_Class triggers and sets correct size flag.
3. Box reaches S_P1 or S_P2 → R_P1/R_P2 fires → P1_Active or P2_Active turns ON.
4. Pusher stays ON for exactly 1 s → turns OFF and Active flag resets.
5. Large boxes counted automatically (no pusher).
6. Retract timeout (3 s) → P1_Fault or P2_Fault sets main Fault and stops system.
7. ResetPB clears faults and counters.

### RAPID Framework Execution
- **Requirements:** Clear, detailed spec
- **AI Generation:** Multiple draft versions
- **Peer Review:** Critical feedback and simplification
- **Iterate & Simulate:** Factory I/O testing → removed complexity
- **Deploy & Document:** Final clean working program + this README

### What I Learned
Fewer lines of code = better maintainability. Rising-edge triggers and simple flags outperform complex state machines for conveyor applications.

**Portfolio Piece** — Demonstrates practical skills in sensor handling, timing, fault management, and clean ladder logic design.

---

Made with the RAPID Engineer Framework  
Ebuka Emmanuel Ajaegbu — April 2026

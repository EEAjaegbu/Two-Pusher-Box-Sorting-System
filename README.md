# Two Pusher Box Sorting System

**Clean PLC automation project in CODESYS + Factory I/O**

**Author:** Ebuka Emmanuel Ajaegbu  
**Date:** 29 April 2026  
**Framework:** RAPID Engineer Framework v2.0

### Objective
Reliable dual-pusher conveyor sorter that classifies boxes (Small/Medium/Large) and diverts them using pneumatic pushers with retract feedback and fault handling.

### Key Features
- Rising-edge classification (S_Low, S_Mid, S_High)
- One-shot memory flags for size
- Position-triggered pushers (S_P1 / S_P2)
- Exact 1.5 s pusher actuation using TON
- Retract feedback with timeout fault detection
- Individual P1/P2 faults + main system fault
- Counters for Small, Medium, and Large boxes
- Clean ResetPB for faults and counters

### Technologies
- **PLC:** CODESYS (Ladder Diagram)
- **Simulator:** Factory I/O
- **Approach:** RAPID Engineer Framework v2.0

### How It Works
1. StartPB → conveyor runs.
2. Box classification via R_TRIG → sets Small_Flag or Medium_Flag.
3. Box reaches pusher position → activates P1_Active or P2_Active.
4. Pusher stays ON for 1.5 s → turns OFF and resets.
5. Large boxes counted automatically.
6. Faults (retract timeout, stuck pusher) stop the system.

### RAPID Framework Execution
- Requirements → clear spec
- AI Generation → multiple drafts
- Peer Review → critical feedback
- Iterate & Simulate → simplified until it worked
- Deploy & Document → final clean code + this README

### What I Learned
Fewer lines of code > complex logic. Rising-edge triggers and memory flags make conveyor systems far more reliable.

**Portfolio Piece** — Demonstrates practical skills in sensor handling, timing, fault management, and clean ladder logic design.

---

Made with the RAPID Engineer Framework  
Ebuka Emmanuel Ajaegbu — April 2026

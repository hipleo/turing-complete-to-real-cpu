# From Turing Complete to a Real 8-Bit CPU

**Goal:** Build a fully functional 8-bit CPU — starting from a video game, ending with real hardware.

**Started:** March 27, 2026 — Grade 10  
**Target:** Working CPU on a PCB by end of Grade 11

---

## The Plan

1. **Turing Complete** — Learn CPU architecture from scratch through the game
2. **Digital (simulator)** — Rebuild the CPU properly in a real EDA tool
3. **PCB design** — Turn the simulation into actual hardware using KiCad
4. **Run Snake** — Prove it works with something real

This repo documents every step, including mistakes.

---

## Progress

| Section | Status | Time Spent |
|---|---|---|
| Basic Logic | Complete | 1.3 hrs |
| Arithmetic & Memory | Complete | 7.4 hrs |
| CPU Architecture | Complete | 9.7 hrs |
| Programming | In Progress | — |
| CPU Architecture 2 | Not Started | — |
| Functions | Not Started | — |
| Assembly Challenges | Not Started | — |
| Digital Simulation | Not started | — |
| PCB Design | Not started | — |
| Assembly | Not started | — |

---

## Chapter 1 — Basic Logic
### March 27, 2026

First session. Finished the entire Basic Logic section in one sitting.

The main thing I learned is something called **functional completeness**, the idea that you can build any logic circuit from nothing but NAND gates. Every AND, OR, XOR, NOT gate that exists can be made from combinations of NAND. This made me understand that everything can be made out of NAND.

The levels started simple, a single NAND gate, and built up to more complex combinations. By the end I was combining gates to build things I didn't fully understand yet but could get working through logic and brute forcing random combinations until something worked.

**Time:** 77 minutes  
**Takeaway:** NAND gates are all you need. Everything else is built on top of them.

#### Screenshots

*Level map — Basic Logic section fully completed (all green):*
![Basic Logic level map](images/01_basic_logic_levelmap.png)

*AND, OR and NAND gate combinations — circuits getting more complex:*
![AND OR NAND gates](images/02_basic_logic_and_or_nand.png)

*XOR gate built from OR, NAND and AND — both inputs split into OR and NAND, their outputs fed into AND:*
![XOR gate](images/03_basic_logic_xor_gates.png)

---

## Chapter 2 — Arithmetic & Memory
### March 30 – April 3, 2026

This section was a completely different difficulty level. Basic Logic felt like a warm-up. Arithmetic and Memory actually made me sit and think for a long time before anything worked.

### March 30 — First 15 Levels

Got through roughly half the section. Learned about bytes, built my first adder, and spent way too long confused about why some levels use bit wires and others use byte wires. The coloured wire system in Turing Complete represents different data widths and I kept mixing them up.

Once I actually understood that bits and bytes are handled by completely different components and you have to convert between them properly, everything became clearer. Should have figured that out sooner but the levels where I was stuck actually taught me more than the easy ones.

**Time:** 2.3 hours

*Progress map mid-way — roughly half complete, locked levels still showing red:*
![Arithmetic Memory progress](images/04_arithmetic_memory_progress.png)

*Full adder — first time building real binary addition from scratch:*
![Full adder circuit](images/05_full_adder.png)

*8-bit adder (Adding Bytes) — chains 8 full adders together to add two full bytes:*
![Adding bytes circuit](images/06_adding_bytes.png)

### April 3 — Section Complete

Finished everything. Built adders, registers, RAM, an input selector, a signed negator, a logic engine, and more. The jump from Basic Logic to this was massive — 5.1 hours in a single section compared to 1.3 hours for the first one.

The final level, **Little Box**, genuinely killed me. The workspace was tiny and I had to build something complex inside it. Spent a long time on it but eventually got it.

**Time:** 5.1 hours  
**Takeaway:** I now understand how memory actually works at the hardware level — registers, load/save signals, addressing, all of it. This wasn't just clicking through puzzles anymore. I had to think for some time before things started to work.

*Section fully completed — all levels green:*
![Arithmetic Memory complete](images/07_arithmetic_memory_complete.png)

*Input Selector — routes one of two 8-bit inputs to the output based on a control signal:*
![Input selector](images/08_input_selector.png)

*Signed Negator — flips the sign of an 8-bit number using two's complement (NOT all bits, then add 1):*
![Signed negator](images/09_signed_negator.png)

*Logic Engine — performs AND, OR, NOT operations on bytes, selected by an opcode:*
![Logic engine](images/10_logic_engine.png)

*Little Box — the final level. Tight space, lots of components, colour-coded everything just to survive it:*
![Little Box](images/11_little_box.png)

---

## Chapter 3 — CPU Architecture 

This is where everything from the first two chapters comes together into an actual CPU. The components I've already built — adders, registers, memory — are the building blocks. Now I'm connecting them into something that can fetch an instruction, decode it, and execute it.

### 13 April 2026 – Section Complete

Finished the entire CPU Architecture chapter! Built and connected every major component: Arithmetic Engine, Registers, Instruction Decoder, Program Counter, and the full control logic. Unlocked the **first working 8-bit computer** — it’s now a complete, functional CPU that can run real programs.  

![CPU Architecture Complete – First Working 8-bit Computer](images/12_First_working_computer.png)

**Biggest takeaway**  
This was the hardest chapter so far. Everything finally came together into one machine. I now have a real 8-bit CPU built completely from NAND gates. The moment the “Working Computer” component lit up felt amazing.

**Next**  
Programming & Assembly chapter — time to actually write code for the computer I just built.

---

## What's Next After the Game

Once the game(at least CPU Architecture 2) is done, the plan is:

**Step 1 — Rebuild in Digital (circuit simulator)**  
Take everything I designed in Turing Complete and rebuild it in [Digital](https://github.com/hneemann/Digital) — a proper EDA simulation tool. This produces clean schematics and lets me verify the design before touching any hardware.

**Step 2 — Design a PCB in KiCad, or an FPGA depending on location and if on break, or both**  
Turn the simulation into a real PCB layout. Order it from JLCPCB. The goal is something small, clean and portable — not a breadboard that falls apart in a bag.

**Step 3 — Write an assembler**  
Define my own instruction set (ISA) and write a Python script that converts human-readable assembly into the binary my CPU runs.

**Step 4 — Run Snake**  
The final proof that the CPU actually works — program it to run Snake. Display output, input handling, game loop, the whole thing.

---

## Resources I've Found Useful

- [Turing Complete](https://store.steampowered.com/app/1444480/Turing_Complete/) — the game this whole project started with
- [Digital](https://github.com/hneemann/Digital) — the simulator I'll use to rebuild the CPU
- [Ben Eater's 8-bit CPU series](https://eater.net/8bit) — YouTube series that heavily inspired the hardware phase
- [KiCad](https://www.kicad.org/) — for PCB design

---

*This project is being documented as it happens. Last updated: April 2026*

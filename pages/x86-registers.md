---
permalink: /x86-registers
layout: default
title: x86 CPU Registers
---

x86 has a lot of registers used for a lot of different tasks. On this wiki, registers are written in all-caps and in a code font (`CR0`, `EFER`, etc). Specific bits in those registers are written with a dot and the bit's label (`CR0.PE`, `CR4.PAE`, `EFER.LME`).

# Control Registers

Control registers enable or disable specific CPU settings in x86. Control registers cannot be written to or read from directly. To read a control register, move its value into another register and read that; to write a control register, move the value from another register into the control register. This example sets the `PE` bit in the `CR0` register:

```asm
; Read CR0
mov eax, cr0
; Set PE (bit 0)
or eax, 1 << 0
; Write CR0
mov cr0, eax
```

## CR0

| Bit | Label                    | Description              |
| --- | ------------------------ | ------------------------ |
| 0   | PE (Protected Enable)    | Turns on protected mode  |
| 1   | MP (Monitor Coprocessor) |                          |
| 2   | EM (Emulate Coprocessor) |                          |
| 3   | TS (Task Switched)       |                          |
| 4   | ET (Extension Type)      | Read-only; cannot be set |
| 5   | NE (Numeric Error)       |                          |
| ... | ...                      | ...                      |
| 16  | WP (Write Protect)       |                          |

## CR1

## CR2

## CR3

## CR4

# Model-Specific Registers

Model-specific registers are 64-bit registers whose availability or location depends on the CPU model. MSRs are identified by a number, and are not read from or written to directly. MSRs are read with the `rdmsr` instruction and written to with the `wrmsr` instruction. Both instructions read the MSR to interact with from the `ECX` register, and read data into or write data from the `EDX:EAX` registers (`EDX` stores the higher 32 bits, `EAX` stores the lower 32 bits).

## EFER

# Sources & Further Reading

- The AMD64 Architecture Programmer's Manual
- <https://wiki.osdev.org/CPU_Registers_x86>

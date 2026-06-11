# Nand2Tetris Assembler

This repository contains my implementation of the Hack Assembler from the Nand2Tetris course.

The assembler translates Hack assembly programs (`.asm`) into Hack machine code (`.hack`) according to the specification defined in Project 6. It supports A-instructions, C-instructions, labels, predefined symbols, and user-defined variables.

## Implementation

The assembler uses a two-pass approach:

* The first pass scans the program and records label definitions in the symbol table.
* The second pass translates instructions into binary machine code while resolving symbols and allocating memory for variables.

The project is split into separate modules for parsing instructions, symbol handling, and binary code generation.

## Supported Features

* A-instructions (`@value`, `@symbol`)
* C-instructions (`dest=comp;jump`)
* Labels (`(LABEL)`)
* Predefined Hack symbols (`SP`, `LCL`, `ARG`, `THIS`, `THAT`, `R0-R15`, `SCREEN`, `KBD`)
* User-defined variables

## Build and Run

Compile:

```bash
gcc assembler.c parser.c writer.c -o assembler
```

Run:

```bash
./assembler input.asm
```

The assembler generates `input.hack` in the same directory.

## Project Structure

```text
assembler.c     Main assembler logic
parser.c        Instruction parsing
writer.c        Binary code generation
*.h             Header files
```

## What I Learned

This project helped me understand assembly language translation, symbol resolution, two-pass assembler design, and the relationship between human-readable assembly code and machine instructions.

## References

* Nand2Tetris
* The Elements of Computing Systems — Noam Nisan and Shimon Schocken

# Nand2Tetris VM Translator

This repository contains my implementation of the VM Translator from the Nand2Tetris course.

The translator converts Virtual Machine (VM) commands into Hack assembly code and supports the complete VM specification, including arithmetic operations, memory access, branching commands, and function calls. It can translate either a single `.vm` file or an entire directory of VM files into Hack assembly.

## Supported Commands

* Arithmetic and logical operations (`add`, `sub`, `neg`, `eq`, `gt`, `lt`, `and`, `or`, `not`)
* Memory access commands (`push`, `pop`)
* Program flow commands (`label`, `goto`, `if-goto`)
* Function commands (`function`, `call`, `return`)
* Bootstrap initialization (`SP = 256`, `Sys.init`)
* Static variables with file-level scope

## Implementation

The project is written in C++ and organized as a single source file containing both the parser and code-generation logic. Labels are generated automatically for comparison operations and function calls, while return-address handling follows the Hack VM specification.

## Running the Translator

Compile:

```bash
g++ -std=c++17 VMTranslator.cpp -o VMTranslator
```

Translate a VM file:

```bash
./VMTranslator SimpleAdd.vm
```

Translate a directory:

```bash
./VMTranslator FunctionCalls/
```

The generated assembly file is written alongside the input file or directory.

## What I Learned

Implementing the translator helped me understand how stack-based virtual machines work internally, how function call frames are managed, and how higher-level VM commands can be mapped to low-level assembly instructions.

## References

* Nand2Tetris
* The Elements of Computing Systems — Noam Nisan and Shimon Schocken


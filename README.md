# Integer Overflow in Assembly Memory Access

This repository demonstrates a potential integer overflow bug in assembly code and its solution.

## Bug Description

The `mov eax, [ebx + ecx*4 + 0x10]` instruction calculates a memory address.  If `ebx`, `ecx`, or the intermediate calculations exceed the maximum value for a 32-bit register, an overflow occurs, resulting in an incorrect memory address being accessed.  This can cause a crash, segmentation fault, or other unpredictable behavior.

## Solution

The solution involves adding checks to ensure the address calculation remains within the valid range before accessing memory.  This might involve using larger registers (64-bit) or range checks.
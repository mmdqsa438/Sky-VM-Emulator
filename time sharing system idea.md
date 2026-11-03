# Sky-VM-Emulator — Development Idea

This project is currently an educational, single-threaded virtual machine. The main development idea is to move it toward a more realistic and faster architecture rather than a simple instruction simulator.

## Key Proposed Changes

- **Add multithreading:** Move the VM beyond single-threaded execution by supporting multiple execution flows, or at least scheduling between them. This requires rethinking registers, memory, and per-thread state management.
- **Replace numeric jumps with labels:** Instead of using absolute addresses and raw numbers for jump instructions, programmers should use readable labels.
- **Build a simple assembler:** The assembler should read textual instructions, parse them, and convert them into numeric machine code. The output should include fields such as opcode, register number, immediate value, and jump target so that execution resembles a real instruction flow.
- **Resolve jump labels in the assembler:** The logic for jump labels should be handled inside the assembler. It should collect labels in one pass and convert them into fixed or relative addresses in the next pass. This makes runtime processing faster and reduces extra computation inside the VM.

## Expected Outcome

The goal is to turn Sky-VM from a simple simulator into a platform where readable assembly programs are written, the assembler converts them into structured machine code, and the virtual machine executes instruction flows in a way that is closer to real processors. Multithreading is considered the next major development step.

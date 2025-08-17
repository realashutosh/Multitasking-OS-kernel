# Multitasking Operating System Kernel (C & Assembly)

This project is a **multitasking operating system kernel** built from scratch using C and Assembly. It focuses on process management, memory protection, and secure execution of user programs.

---

## Features

- **Process Management:**

  - Cooperative and preemptive multitasking.
  - Process scheduling for fair CPU time distribution.
  - Secure termination of misbehaving processes.

- **Memory Management:**

  - Virtual memory system with address translation (virtual → physical).
  - Page-based memory management.
  - Enforced kernel–user land separation using hardware protection rings.

- **Kernel Design:**

  - Linux-inspired modular kernel design patterns.
  - Improved maintainability, modularity, and system performance.
  - Clear separation of kernel subsystems (scheduling, memory, I/O).

- **Debugging & Testing:**

  - Integrated with QEMU emulator for rapid prototyping.
  - Used GDB for low-level debugging, disassembly inspection, and step-by-step kernel execution.

---

## Requirements

- **Toolchain:**
  - `gcc` / `clang` (cross-compiler targeting i386 or x86\_64)
  - `nasm` or `as` for assembling low-level routines
- **Emulation & Debugging:**
  - QEMU (hardware emulation)
  - GDB (kernel debugging)

---

## Build Instructions

1. Clone or download the repository.
2. Build the kernel using the provided Makefile:
   ```bash
   make
   ```
3. Run the kernel in QEMU:
   ```bash
   qemu-system-i386 -kernel kernel.bin
   ```
4. (Optional) Debug with GDB:
   ```bash
   qemu-system-i386 -s -S -kernel kernel.bin
   gdb -ex "target remote localhost:1234" kernel.elf
   ```

---

## Usage

- The kernel boots into a simple shell-like interface or demo program (depending on configuration).
- Multiple user programs can be spawned, scheduled, and terminated securely.
- Virtual memory mapping ensures that each process runs in isolated memory space.

---

## Notes

- This project is for **educational purposes** and not intended as a production OS.
- For best results, run inside QEMU (tested on Linux/macOS).
- Windows users can use WSL2 with QEMU for building and testing.

---

## License

This project is open-source and free to use, modify, and distribute for research and educational purposes.

# EndlOS - A Simple Operating System from Scratch

EndlOS is a minimalist operating system written in C and Assembly that implements basic OS functionality including graphics, window management, input handling, and task scheduling.

## Features

- **Custom Bootloader**: Written in Assembly to initialize the system and switch to protected mode.
- **Graphics System**:
  - Basic pixel drawing and shape rendering.
  - Custom font rendering.
  - Double buffering for smooth graphics.
- **Window Management**:
  - Movable windows.
  - Window controls (close button).
  - Taskbar.
- **Input Handling**:
  - Mouse support with a custom cursor.
  - Keyboard input.
  - Event system.
- **Task Management**:
  - Simple task scheduler.
  - Priority-based execution.
  - Multiple concurrent tasks.

## Prerequisites

To build and run EndlOS, you'll need:
- NASM (Netwide Assembler)
- GCC (with 32-bit support)
- LD (GNU Linker)
- QEMU (for emulation)
- Make

### Ubuntu/Debian Setup

```bash
# Commands for Ubuntu/Debian setup

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

```
sudo apt-get update
sudo apt-get install nasm gcc-multilib qemu-system-x86 make
```


### Windows Setup

- Install NASM
- Install MinGW (ensure you get the 32-bit version)
- Install QEMU
- Add all executables to your system PATH

### Building

- The project uses a simple Makefile for building. The build process:
- Assembles the bootloader
- Compiles the kernel
- Links everything together
- Creates the final disk image

```
all: bootloader

bootloader:
	nasm boot/boot.asm -f bin -o boot/bin/boot.bin
	nasm boot/kernel_entry.asm -f elf -o boot/bin/kernel_entry.bin
	
	gcc -m32 -ffreestanding -c boot/final.c -o boot/bin/kernel.o
	ld -m elf_i386 -o boot/bin/kernel.img -Ttext 0x1000 boot/bin/kernel_entry.bin boot/bin/kernel.o

	objcopy -O binary -j .text boot/bin/kernel.img boot/bin/kernel.bin
	cat boot/bin/boot.bin boot/bin/kernel.bin > os.img
```


### To build:

```
make
```

### Running

- To run in QEMU

```
make run
```

### Project Structure
```
boot/
  ├── boot.asm             # Bootloader implementation
  ├── kernel_entry.asm     # Kernel entry point
  ├── main.c               # Main kernel code
  ├── graphics.c           # Graphics implementation
  ├── input.c              # Input handling
  ├── task.c               # Task scheduler
  ├── graphics_elements.c   # UI elements
  ├── font.c               # Font definitions
  └── graphics.h           # Graphics declarations
```

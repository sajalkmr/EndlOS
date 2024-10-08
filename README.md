# GUI OS

A simple operating system with a graphical user interface, built from scratch.

## Description

This project is an attempt to create a basic operating system with a GUI. It starts with a bootloader that switches from real mode to protected mode, work in progress.

## Prerequisites

Before you begin, ensure you have the following installed:

- NASM (Netwide Assembler)
- GCC (GNU Compiler Collection)
- QEMU (Quick Emulator)

On Ubuntu or Debian-based systems, you can install these with:

```bash
sudo apt-get update
sudo apt-get install nasm gcc qemu qemu-kvm
```

## Building the Project

To build the bootloader:
```bash
make
```


This will compile the `boot.asm` file and create a `boot.img` file in the `boot` directory.

## Running the OS

To run the OS in QEMU:
```bash
make run
```


This command will start QEMU and boot your OS image.

## Cleaning Up

To remove the compiled files:
```bash
make clear
```


## Project Structure

- `boot/boot.asm`: The main bootloader code
- `Makefile`: Contains commands for building and running the project
- `README.md`: This file, containing project information and instructions

## Features

- Bootloader that switches from 16-bit real mode to 32-bit protected mode
- Clears the screen and displays a welcome message
- Sets up Global Descriptor Table (GDT)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

[MIT License](LICENSE)

## Acknowledgments

- NASM documentation
- QEMU documentation
- OS Development community


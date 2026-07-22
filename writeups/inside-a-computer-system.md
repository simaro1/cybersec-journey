# TryHackMe: [Inside a Computer System]

**Date:** July 22 2026
**Path:** Pre-Security

## What it covered
Needing to know what's inside a computer
What's inside a computer: Motherboard(Skeleton and nerves), RAM: Short term memory, PSU: "Heart and lungs"
CPU: The brains, GPU: Visual cortex, HDD+SSD: Long-term Memory

## What I learned
Every computer includes the same building blocks
The specific building blocks:
Motherboard allows communication between the different parts. It holds them in place and connects them. 
CPU(Central processing Unit), or the processor, executes instructions, has multiple cores that handles multiple instructions at the same time, connected via CPU socket.
RAM holds data that the CPU can access quickly. Uses tech like DDR5 or DDR6 for better performance. 
SSD HDD's holds data long term or permanently even when system is off. Use memory chips. 
Network Adapter connected through PCI express ports, allow computers to speak with other computers
PSU(Power supply) provides power to everything
GPU outputs visual displays
Input/output devices send and receive data from computers. Mouse, keyboard, USB, HDMI etc. 

When we boot up a system, the firmware starts, then the POST, then select boot devic then start bootloader
Power button sends signal to PSU to allow flow
Firmware allows the components to start, known as UEFI but more commonly known as BIOS
Then the power on self test tests if every component is here and working correctly
Then the UEFI holds a list to prioritize which device to look for for the routine in the OS.
Then it initiates the bootloader which transfers the OS boot device to the RAM. once the OS is transferred, UEFI gives control to the OS.


## Something that tripped me up


## Commands / notes I want to remember
```

```

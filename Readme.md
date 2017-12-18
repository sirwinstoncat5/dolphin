# Porpoiise - my crazy Dolphin-based Wii U project

Porpoiise aims to run Wii games on Wii U without rebooting into vWii. Eventually, this will use the newer GX2 GPU, possibly allowing for rendering tricks previously available only with traditional emulators.

Development will be heavily based upon Dolphin's framework; as such, it's licensed as GPLv2+. This repo is currently just a clone of dolphin-emu/dolphin, but this will change soon.

Current roadmap:
1. Modify Dolphin. (This development stage can be run on any big-endian hardware, optimally something like a PowerPC 750; I'm using an iMac G3.) 
** Strip Dolphin of extras (GUI, etc.)
** Add big-endian support.
** Fix other compatibility errors as they are found. (Ambiguous, but it has to be.)
2. Write "hypervisor" CPU backend. (This MUST be run on something compatible to the Wii/Wii U instruction set, such as a PowerPC 750.)
** Run as many instructions possible on bare metal.
** Trap unsafe instructions and execute a workaround. (eg. memory access)
3. Shift codebase to run on Wii U.
** At first: run interpreter CPU backend and software GPU backend.
** Later: attempt to run and improve hypervisor CPU backend.
4. Write GX -> GX2 GPU backend.
** Start with Dolphin's OpenGL backend.
** Convert OpenGL commands to work with GX2.
** Interface backend with hypervisor CPU backend's GPU FIFO

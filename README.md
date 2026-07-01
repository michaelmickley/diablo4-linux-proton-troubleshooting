# Diablo IV on Linux: Proton Troubleshooting and Custom Wine Workaround

## Table of Contents

- [My System](#my-system)
- [The Problem](#the-problem)
- [Research](#research)
- [Troubleshooting Process](#troubleshooting-process)
- [What I Learned](#what-i-learned)
- [Skills Used](#skills-used)
- [Current Status](#current-status)
- [Result](#result)

## Overview

When Diablo IV stopped launching after the Season 14 update, I decided to investigate the problem instead of waiting for an official fix.

My goal was to understand why the game stopped working and learn more about how Proton and Wine interact on Linux. During the troubleshooting process I researched community solutions, tested multiple Proton versions, built patched Wine DLLs, and created a custom Steam compatibility tool.

I created this repository to document the troubleshooting process, record what I learned, and have a reference for future Linux compatibility issues.

---

## My System

- Operating System: Pop!_OS 24.04
- Desktop Environment: COSMIC
- CPU: AMD Ryzen 7 9800X3D
- GPU: NVIDIA GeForce RTX 5080
- Driver Version: 580.159.03
- Platform: Steam
- Game: Diablo IV

---

## The Problem

After the Season 14 update, Diablo IV would no longer start on Linux.

Instead, Steam displayed the following error:

```
Failed to load function

Module:
KERNEL32.dll

Import:
FindNextFileNameW

Error Code: 127
Procedure not found
```

---

## My Goal

Rather than waiting for an official update, I wanted to:

- Understand why the game stopped working
- Learn how Proton and Wine interact
- Test community fixes
- Document everything I learned
- Build something I could include in my portfolio

---

## Investigation Timeline

## Initial Checks

I first verified that my system was working correctly.

I checked:

- NVIDIA driver installation
- Vulkan support
- Steam installation
- Proton versions
- Wine configuration
- Game files

None of these solved the issue.

---

## Research

I spent time reading GitHub discussions, Reddit posts, ProtonDB reports, and Linux gaming communities.

From those discussions I learned that Blizzard had started using a Windows API called:

FindNextFileNameW

Current Proton builds did not export this function, causing Diablo IV to fail before it could launch.

---

## Testing

During troubleshooting I tested:

- Proton Experimental
- GE-Proton 11
- CachyOS Proton
- Fresh game installation
- Removing compatibility prefixes
- Multiple launch attempts
- Proton logging

---

## Building the Workaround

Using a community patch, I:

- Cloned the patched repository
- Initialized the Wine submodule
- Generated the Wine configure script
- Built the patched DLL files
- Created a custom Steam compatibility tool
- Installed the patched DLLs into Proton

This allowed me to better understand how Proton is structured and how Steam compatibility tools work.

---

## What I Learned

Before this project I had never:

- Built Wine from source
- Patched DLL files
- Modified a Proton compatibility tool
- Used Git for a troubleshooting project

This project gave me experience reading technical documentation, following build instructions, troubleshooting Linux software, and understanding how different components work together.

---

## Skills Used

- Linux
- Bash
- Git
- GitHub
- Steam
- Proton
- Wine
- Vulkan
- NVIDIA Drivers
- Software Troubleshooting
- Research
- Documentation

---

## Current Status

The project is still ongoing while official Proton fixes continue to be released.

Regardless of the final solution, this project has been valuable for learning Linux troubleshooting and documenting my process.

---

## Result

After building the patched Wine DLLs and creating a custom Proton compatibility tool, Diablo IV successfully launched on Pop!_OS without replacing my existing Proton installation.

![Diablo IV Running](screenshots/04-game-working.png)

# Day 1

## Goal

Get Diablo IV working again on Pop!_OS after the Season 14 update.

## Initial Problem

The game would not launch through Steam.

Error:

```
Failed to load function

Module:
KERNEL32.dll

Import:
FindNextFileNameW

Error Code:
127
```

## What I Tried

- Verified game files
- Tried multiple Proton versions
- Installed ProtonUp-Qt
- Installed GE-Proton 11-1
- Installed CachyOS Proton
- Read GitHub issues
- Read Reddit discussions
- Built patched Wine DLLs
- Created a custom Steam compatibility tool

## Result

Successfully launched Diablo IV using a custom Proton compatibility tool containing patched Wine DLLs.

## What I Learned

- How Proton works
- How Wine provides Windows APIs
- How Steam compatibility tools are structured
- Basic Wine source compilation
- Using Git to clone repositories
- Applying patches with Git
- Troubleshooting Linux game compatibility

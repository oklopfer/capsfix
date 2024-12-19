# capsfix

A script to fix the nuisance of Caps Lock disable not toggling until key release.

## The Problem

On modern Windows and macOS machines, the caps lock states are as follows:

```
Unpressed (off) -> Pressed (on) -> Released (on) -> Pressed (off) -> Released (off)
```


Meaning, as one would expect, the caps lock on/off states are switched as soon as you press the key, just as any other key on the keyboard.

***However...***

On modern Linux machines, the caps lock states are:

```
Unpressed (off) -> Pressed (on) -> Released (on) -> Pressed (on) -> Released (off)
```

Meaning while the on state is switched as soon as you press the key, the off state is not, and only turns off on release. So long as caps lock is being pressed, it is always in the on state.

Why? Something to do with "that's how it was on typewriters," idk...

Will this annoyance ever have a meaningful effect in practical settings? Probably not. But it is still annoying.

## The Solution

The original solution is found and explained in this wiki post: https://wiki.archlinux.org/title/Xorg/Keyboard_configuration#Switching_state_immediately_when_Caps_Lock_is_pressed

This script allows for:
- quick starting and stopping of the immediate switching
    - where possible, your normal caps lock state will be saved to `~/.config/xkb_caps_backup`

- enabling and disabling it as persistent, per user (through an autostart `.desktop`)
    - It will only modify the keymap for the current session if just starting and stopping
 
**NOTE:** Currently only works in X11. Wayland solution to come.

## Installation

### Requirements

- `bash`
- `cat`
- `perl`
- Debian/Ubuntu: `x11-xkb-utils` / Arch: `xorg-xkbcomp`

### 

```bash
git clone https://github.com/oklopfer/capsfix.git
sudo cp capsfix/capsfix /usr/bin
```

## Usage

```bash
capsfix {enable|disable|start|stop}
```

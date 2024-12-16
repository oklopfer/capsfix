# capsfix

A script to fix the nuisance of Caps Lock disable not toggling until key release.

## Requirements

- `bash`
- `cat`
- `perl`
- `x11-xkb-utils` (Debian/Ubuntu)/`xorg-xkbcomp` (Arch)

## Installation

```bash
git clone https://github.com/oklopfer/capsfix.git
sudo cp capsfix/capsfix /usr/bin
```

## Usage

```bash
capsfix {enable|disable|start|stop}
```

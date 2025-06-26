# Dotfiles

> My personal Linux configuration files to setup my environment on Arch Linux.

---

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [1. Update and install packages](#1-update-and-install-packages)
  - [2. Clone this repository](#3-clone-this-repository)
  - [3. Apply configurations with GNU Stow](#4-apply-configurations-with-gnu-stow)
  - [4. Set fish as default shell](#5-set-fish-as-default-shell)
  - [5. Reboot](#6-reboot)
- [Usage](#usage)
- [Updating your configs](#updating-your-configs)
- [Adding new application configs](#adding-new-application-configs)
- [Troubleshooting](#troubleshooting)

---

## Introduction

This repository contains my `.config` files and other dotfiles for applications like `hyprland`, `waybar`, `wofi`, `kitty`, `alacritty`, `fish` shell, and system settings.

---

## Prerequisites

- A fresh Arch Linux install (or compatible)
- Internet connection
- Basic familiarity with Linux commands and terminal

---

## Installation

### 1. Update and install packages

Update your system and install all required packages:

```bash
sudo pacman -Syu --noconfirm
sudo pacman -S --needed --noconfirm \
git stow fish kitty alacritty nautilus dconf ibus pulseaudio \
gnome-session gtk3 go yay hyprland waybar wofi xdg-desktop-portal-hyprland
```

---

### 3. Clone this repository

Clone your dotfiles repository to your home folder.

- Using HTTPS:

```bash
git clone https://github.com/AlessandroPerez/dotfiles.git ~/dotfiles
```

Change directory into your dotfiles folder:

```bash
cd ~/dotfiles
```

---

### 4. Apply configurations with GNU Stow

GNU Stow will symlink all configuration folders into your home directory.

Run:

```bash
stow *
```

> [!WARNING] 
> If you receive errors about existing files or directories, backup the conflicting configs first. For example:

```bash
mv ~/.config/fish ~/.config/fish.bak
stow fish
```

---

### 5. Set fish as default shell

Change your default shell to fish:

```bash
chsh -s /usr/bin/fish
```

> [!IMPORTANT]   
> You must log out and log back in (or reboot) for this change to take effect.

---

### 6. Reboot

Restart your system to ensure all configurations are properly loaded:

```bash
sudo reboot
```

---

## Usage

After reboot, your system will be configured with:

- `fish` shell as default
- `hyprland` as the window manager
- Configured terminals (`kitty`, `alacritty`)
- Waybar, Wofi, and other UI elements with your preferred settings

You can now continue customizing or using the setup as is.

---

## Updating your configs

Whenever you modify configs, save your changes and push them back to GitHub:

```bash
cd ~/dotfiles
git status
git add .
git commit -m "Describe your changes"
git push
```

---

## Adding new application configs

To add a new application's config:

```bash
mkdir -p newapp/.config
mv ~/.config/newapp newapp/.config/
stow newapp
git add .
git commit -m "Add newapp config"
git push
```

---

## Troubleshooting

- If `stow` complains about existing files:

```bash
mv ~/.config/fish ~/.config/fish.bak
stow fish
```

- If SSH cloning fails, check your SSH key on GitHub or use HTTPS cloning.

---

> **Enjoy your new setup!** 🚀

---

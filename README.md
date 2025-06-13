# Alessandro's Dotfiles

> My personal Linux configuration files to setup my environment on Arch Linux.

---

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [1. Update and install packages](#1-update-and-install-packages)
  - [2. Setup SSH keys (optional but recommended)](#2-setup-ssh-keys-optional-but-recommended)
  - [3. Clone this repository](#3-clone-this-repository)
  - [4. Apply configurations with GNU Stow](#4-apply-configurations-with-gnu-stow)
  - [5. Set fish as default shell](#5-set-fish-as-default-shell)
  - [6. Reboot](#6-reboot)
- [Usage](#usage)
- [Updating your configs](#updating-your-configs)
- [Adding new application configs](#adding-new-application-configs)
- [Troubleshooting](#troubleshooting)

---

## Introduction

This repository contains my `.config` files and other dotfiles for applications like `hyprland`, `waybar`, `wofi`, `kitty`, `alacritty`, `fish` shell, and system settings.

Following the instructions below on a fresh Arch Linux install will reproduce my entire setup **without the need for additional steps or commands**.

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


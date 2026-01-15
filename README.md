# Event Horizon Dotfiles

My personal desktop environment setup for Linux, built on Hyprland and Quickshell. It's basically a complete desktop experience that I've been tweaking and refining over time.

## What is this?

This started as [DankMaterialShell](https://github.com/AvengeMedia/DankMaterialShell) dotfiles but has grown into my own full desktop environment setup. I'm using Hyprland as the window manager (it's a tiling Wayland compositor) and Quickshell for the shell/widget system. Together they make for a pretty solid desktop experience.

**Includes:** All necessary fonts (SF Pro, Inter, Fira Code, Material Symbols, Noto) are bundled with the configuration files.

## Screenshots

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/45817183-4b9b-481f-a928-a00a2280bc65" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/89cbcbd3-491e-4b7d-bd03-92ca91adf62e" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/6caf4ba3-3611-4c21-8d7a-4e7300bac340" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/a86a55d7-0f40-4eb4-b504-e78707bd5bf8" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/22c72af2-aa8a-442e-9f0e-4580cd44063c" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/4e0439f9-b45f-4502-9743-e13b0c798c4e" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/954f8b9c-9d2a-41ed-aeb2-e28647e7b098" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/a56e7b63-4367-42ee-a6d3-5e07bf124573" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/95786a09-a524-486a-abc0-a51dacd21ad1" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/b01eb71c-d5e8-4471-9f84-d471f0661912" />



## Quick Start

### Automatic Installation (Recommended)

Run the universal installer - it auto-detects your distribution and installs everything:

```bash
./install.sh
```

The installer will:
- ✅ **Ask for confirmation** before starting installation
- ✅ Auto-detect your Linux distribution (Arch, Fedora, Ubuntu, Debian, PikaOS)
- ✅ Check for already installed packages and skip them
- ✅ Handle sudo permissions automatically
- ✅ Install all required dependencies
- ✅ **Automatically copy config files** to ~/.config/hypr/ and ~/.config/quickshell/
- ✅ **Backup existing configs** to .bak folders (only on first install)
- ✅ Provide fallbacks if matugen or dgop compilation fails
- ✅ Continue installation even if some components fail

### Manual Installation

If you prefer manual installation, use the [Installation Guide](docs/installation.md) and pick your distro page.

## Next Steps

1. Your DarkMatter setup is ready! Config files are automatically installed.
2. Check out the [Features](docs/features.md) documentation
3. Read the [Hypr Configuration](hypr-configuration.md) guide to customize things
4. Your previous configs are backed up as `.bak` folders if you need to restore them

## Documentation

### Installation

**Universal Installer (Recommended):** Run `./install.sh` - auto-detects your distro and handles everything!

**Manual Installation:** See the [Installation Guide](docs/installation.md) and use the distro-specific pages:

- [Arch Linux and derivatives (CachyOS, EndeavourOS, XeroLinux)](docs/installation-arch.md)
- [Fedora and derivatives (Nobara)](docs/installation-fedora.md)
- [PikaOS](docs/installation-pikaos.md)

Covers all packages, fonts, and post-installation setup.

### [Features](docs/features.md)

What's included in this setup:

- Desktop stuff (top bar, dock, control center)
- System integration (audio, displays, network, power)
- Various utilities
- Customization options
- Application support

### [Hypr Configuration](docs/hypr-configuration.md)

How the Hyprland config is organized:

- File structure and what goes where
- How to customize things
- Window rules and keybinds
- Monitor setup
- Shader effects

## Supported Distributions

I've tested this on:

- **Arch Linux** (and derivatives)
- **Fedora** (and derivatives)
- **PikaOS**

Other distros might work, but I haven't tested them and can't help if something breaks.

## What's Inside

- **Hyprland** - The window manager (tiling Wayland compositor)
- **Quickshell** - Shell system with widgets and launchers
- **Material You** theming using matugen
- System integration for audio, network, displays, etc.
- Lots of customization options

## License

This was originally inspired by [DankMaterialShell](https://github.com/AvengeMedia/DankMaterialShell), but I've rewritten everything and it's no longer a fork. The design keeps changing as I tweak things.

Do whatever you want with it. Fork it, modify it, use parts of it - I don't care about attribution.

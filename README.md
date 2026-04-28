
# Event Horizon Dotfiles
<img width="512" height="412" alt="Event-Horizon-logo" src="https://github.com/user-attachments/assets/c1e8e3cf-fda4-4059-9f9a-a0e7c692edf2" />
My personal desktop environment setup for Linux, built on Hyprland and Quickshell. It's basically a complete desktop experience that I've been tweaking and refining over time.

## What is this?

This started as [DankMaterialShell](https://github.com/AvengeMedia/DankMaterialShell) dotfiles but has grown into my own full desktop environment setup. I'm using Hyprland as the window manager (it's a tiling Wayland compositor) and Quickshell for the shell/widget system. Together they make for a pretty solid desktop experience.

**Includes:** All necessary fonts (SF Pro, Inter, Fira Code, Material Symbols, Noto) are bundled with the configuration files.

## Reporting Issues

Found a bug or have an issue? Please check the [Reporting Guide](docs/reporting-issues.md) for how to submit a good bug report.

## Quick Start

### Automatic Installation (Recommended)

1. Go to the Latest [Release](https://github.com/ryzendew/Event-Horizon-Dotfiles-Issue/releases)

2. **Download the newest `.zip` file.**

3. **Extract** the `.zip` you just downloaded.

4. Open the new folder it created.

5. **Right‑click** inside the empty space of that folder and choose **“Open in Terminal.”**

6. Run the installer:

   ```bash
   ./install.sh


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

## License

This was originally inspired by [DankMaterialShell](https://github.com/AvengeMedia/DankMaterialShell), but I've rewritten everything and it's no longer a fork. The design keeps changing as I tweak things.

Do whatever you want with it. Fork it, modify it, use parts of it - I don't care about attribution.

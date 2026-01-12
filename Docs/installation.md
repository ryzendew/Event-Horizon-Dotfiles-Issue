# Installation Guide

Here's how to get DarkMatter Shell set up on your system. The process is a bit different depending on what distro you're running.

## Installation by Distribution

### Arch Linux / CachyOS / EndeavourOS / XeroLinux

#### Step 1: Update System

First, make sure your system is up to date:

```bash
sudo pacman -Syu
```

#### Step 2: Install Official Repository Packages

```bash
sudo pacman -S brightnessctl cliphist easyeffects firefox fuzzel gedit grim mission-center nautilus nwg-look pavucontrol polkit polkit-gnome mate-polkit ptyxis qt6ct slurp swappy tesseract wl-clipboard xdg-desktop-portal-hyprland yad qt6-5compat xorg-xhost
```

#### Step 3: Install AUR Helper (if needed)

You'll need an AUR helper. I use `yay`, so install it if you don't have it already:

```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay && makepkg -si && cd .. && rm -rf yay
```

#### Step 4: Install AUR Packages

```bash
yay -S anyrun dgop hyprpicker matugen-git python-pynvml quickshell-git wlogout hyprland
```

Or build it yourself if you prefer:

```bash
# Install Go if you don't have it
sudo pacman -S --needed go

# Build it
cd /tmp
git clone https://github.com/AvengeMedia/dgop.git
cd dgop
make
sudo make install
cd .. && rm -rf dgop
```

#### Step 5: Install Fonts

Jump down to the [Font Installation](#font-installation) section.

---

### Fedora / Nobara

#### Step 1: Update System

```bash
sudo dnf update -y
```

#### Step 2: Enable Required Repositories

You'll need RPM Fusion for some packages:

```bash
sudo dnf install -y https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install -y https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

And enable these COPR repos:

```bash
sudo dnf copr enable -y lionheartp/Hyprland
sudo dnf copr enable -y errornointernet/quickshell
```

Update your package cache:

```bash
sudo dnf makecache
```

#### Step 3: Install Packages from COPR Repositories

From the Hyprland COPR:

```bash
sudo dnf install -y hyprland hyprpicker swww xdg-desktop-portal-hyprland
```

From the Quickshell COPR:

```bash
sudo dnf install -y quickshell-git
```

#### Step 4: Install Everything Else

Here's the big package install command:

```bash
sudo dnf install -y hyprland hyprpicker swww xdg-desktop-portal-hyprland xdg-desktop-portal-wlr xdg-desktop-portal-gnome gnome-keyring brightnessctl cliphist easyeffects firefox fuzzel gedit gnome-disks gnome-system-monitor gnome-text-editor grim nautilus nwg-look pavucontrol polkit mate-polkit ptyxis qt6ct slurp swappy tesseract wl-clipboard wlogout yad quickshell-git rust cargo gcc gcc-c++ pkg-config openssl-devel libX11-devel libXcursor-devel libXrandr-devel libXi-devel mesa-libGL-devel fontconfig-devel freetype-devel expat-devel cairo-gobject cairo-gobject-devel rust-gdk4-sys+default-devel gtk4-layer-shell-devel qt5-qtgraphicaleffects qt6-qt5compat python3-pyqt6 python3.11 python3.11-libs libxcrypt-compat libcurl libcurl-devel apr fuse-libs fuse btop lm_sensors gedit nwg-look
```

#### Step 5: Python Dependencies

```bash
pip install pynvml
```

#### Step 6: dgop

Build it from source:

```bash
# Get Go and build tools
sudo dnf install -y golang git make

# Build it
cd /tmp
git clone https://github.com/AvengeMedia/dgop.git
cd dgop
make
sudo make install
cd .. && rm -rf dgop
```

#### Step 7: matugen

Install via Cargo:

```bash
# Install Rust if needed
sudo dnf install -y rust cargo

# Install matugen
cargo install matugen
```

#### Step 8: Install Fonts

See the [Font Installation](#font-installation) section below.

---

### PikaOS

#### Step 1: Update System

```bash
sudo apt update && sudo apt upgrade -y
```

#### Step 2: Install All Packages

Install all required packages in a single command:

```bash
sudo apt install -y --no-install-recommends hyprland-git swww xdg-desktop-portal-hyprland xdg-desktop-portal-wlr xdg-desktop-portal-gnome gnome-keyring brightnessctl cliphist easyeffects firefox fuzzel gedit gnome-system-monitor gnome-text-editor grim nautilus nwg-look pavucontrol mate-polkit-bin ptyxis qt6ct slurp swappy tesseract-ocr wl-clipboard wlogout yad rustc cargo gcc g++ pkg-config libssl-dev libx11-dev libxcursor-dev libxrandr-dev libxi-dev libgl1-mesa-dev libfontconfig-dev libfreetype-dev libexpat1-dev curl unzip fontconfig libcairo2-dev libgtk-4-dev libgtk-layer-shell-dev qtbase5-dev qt6-base-dev python3-pyqt6 python3 python3-dev libcurl4-openssl-dev fuse libfuse2t64 btop lm-sensors golang-go make python3-pip quickshell-git qml6-module-qtquick-controls qml6-module-qtcore qml6-module-qtquick-effects qml6-module-qt5compat-graphicaleffects qml6-module-qt-labs-folderlistmodel qml6-module-qt-labs-platform
```

**Note:** Some packages like `hyprpicker` and `quickshell-git` might not be in the PikaOS repos. You may need to build them from source or find another way to install them.

#### Step 3: Python Dependencies

```bash
pip install pynvml --break-system-packages
```

#### Step 4: dgop (Manual Installation)

Build from Source:

```bash
# Install Go and build tools if not already installed
sudo apt install -y golang-go make

# Clone and build
cd /tmp
git clone https://github.com/AvengeMedia/dgop.git
cd dgop
make
sudo make install
cd .. && rm -rf dgop
```

#### Step 5: matugen (Manual Installation)

Install via Cargo:

```bash
# Install Rust and Cargo if not already installed
sudo apt install -y rustc cargo

# Install matugen
cargo install matugen
```

#### Step 6: Install Fonts

See the [Font Installation](#font-installation) section below.

---

## Font Installation

### Inter Variable Font

```bash
curl -L "https://github.com/rsms/inter/releases/download/v4.0/Inter-4.0.zip" -o /tmp/Inter.zip
unzip -j /tmp/Inter.zip "InterVariable.ttf" "InterVariable-Italic.ttf" -d ~/.local/share/fonts/
rm /tmp/Inter.zip && fc-cache -f
```

### Fira Code

```bash
curl -L "https://github.com/tonsky/FiraCode/releases/download/6.2/Fira_Code_v6.2.zip" -o /tmp/FiraCode.zip
unzip -j /tmp/FiraCode.zip "ttf/*.ttf" -d ~/.local/share/fonts/
rm /tmp/FiraCode.zip && fc-cache -f
```

### Material Symbols

**For Arch Linux:**

AUR:

```bash
yay -S ttf-material-symbols-variable-git
```

**For Fedora and PikaOS:**

Manual installation:

```bash
mkdir -p ~/.local/share/fonts
curl -L "https://github.com/google/material-design-icons/raw/master/variablefont/MaterialSymbolsRounded%5BFILL%2CGRAD%2Copsz%2Cwght%5D.ttf" -o ~/.local/share/fonts/MaterialSymbolsRounded.ttf
fc-cache -f
```

### Noto Fonts

**Arch Linux:**

```bash
sudo pacman -S noto-fonts noto-fonts-emoji
```

**Fedora:**

```bash
sudo dnf install -y google-noto-fonts google-noto-emoji-fonts
```

**Note:** SF Pro Display and SF Pro Rounded are included in `quickshell/eqsh/media/fonts/` and don't need separate installation.

---

## Post-Installation

After you've installed everything, run this:

```bash
xdg-user-dirs-update
```

This makes sure your user directories are set up properly.

---

## Next Steps

Once everything is installed:

1. Copy the config files to your system (usually `~/.config/hypr/` and `~/.config/quickshell/`)
2. Check out the [Features](features.md) doc to see what's included
3. Read the [Hypr Configuration](hypr-configuration.md) guide to customize things


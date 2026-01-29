# Arch Linux / CachyOS / EndeavourOS / XeroLinux Installation

Follow these steps to install DarkMatter Shell on Arch-based distros.

## Step 1: Update System

First, make sure your system is up to date:

```bash
sudo pacman -Syu
```

## Step 2: Install Official Repository Packages

```bash
sudo pacman -S hyprland quickshell brightnessctl cliphist easyeffects firefox fuzzel gedit grim mission-center nautilus nwg-look pavucontrol polkit polkit-gnome mate-polkit ptyxis qt6ct slurp swappy tesseract wl-clipboard xdg-desktop-portal-hyprland yad qt6-5compat xorg-xhost jq matugen
```

## Step 3: Install AUR Helper (if needed)

You'll need an AUR helper. I use `yay`, so install it if you don't have it already:

```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay && makepkg -si && cd .. && rm -rf yay
```

## Step 4: Install AUR Packages

```bash
yay -S anyrun dgop python-pynvml wlogout
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

## Step 5: Install Fonts

Fonts are included with the config, but install them system-wide if you want.

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

AUR:

```bash
yay -S ttf-material-symbols-variable-git
```

### Noto Fonts

```bash
sudo pacman -S noto-fonts noto-fonts-emoji
```

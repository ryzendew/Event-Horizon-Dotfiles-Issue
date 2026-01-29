# Fedora / Nobara Installation

Follow these steps to install DarkMatter Shell on Fedora-based distros.

## Step 1: Update System

```bash
sudo dnf update -y
```

## Step 2: Enable Required Repositories

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
## Step 3: Install Everything Else

Here's the big package install command:

```bash
sudo dnf install -y hyprland hyprpicker swww xdg-desktop-portal-hyprland gnome-keyring brightnessctl cliphist fuzzel gedit gnome-disks gnome-system-monitor gnome-text-editor grim nautilus nwg-look pavucontrol polkit mate-polkit ptyxis qt6ct slurp swappy tesseract wl-clipboard wlogout yad quickshell qt5-qtgraphicaleffects qt6-qt5compat python3-pyqt6 btop gedit nwg-look quickshell jq
```

## Step 4: Python Dependencies

```bash
pip install pynvml
```

## Step 5: dgop

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

## Step 6: matugen

Install via Cargo:

```bash
# Install Rust if needed
sudo dnf install -y rust cargo

# Install matugen
cargo install matugen
```

## Step 7: Install Fonts

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

Manual installation:

```bash
mkdir -p ~/.local/share/fonts
curl -L "https://github.com/google/material-design-icons/raw/master/variablefont/MaterialSymbolsRounded%5BFILL%2CGRAD%2Copsz%2Cwght%5D.ttf" -o ~/.local/share/fonts/MaterialSymbolsRounded.ttf
fc-cache -f
```

### Noto Fonts

```bash
sudo dnf install -y google-noto-fonts google-noto-emoji-fonts
```

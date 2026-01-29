# PikaOS Installation

Follow these steps to install DarkMatter Shell on PikaOS.

## Step 1: Update System

```bash
sudo apt update && sudo apt upgrade -y
```

## Step 2: Install All Packages

Install all required packages in a single command:

```bash
sudo apt install -y --no-install-recommends hyprland swww xdg-desktop-portal-hyprland gnome-keyring brightnessctl cliphist fuzzel gedit gnome-system-monitor gnome-text-editor grim nautilus nwg-look pavucontrol mate-polkit-bin ptyxis qt6ct slurp swappy tesseract-ocr wl-clipboard wlogout yad qtbase5-dev qt6-base-dev python3-pyqt6 python3-pip quickshell qml6-module-qtquick-controls qml6-module-qtcore qml6-module-qtquick-effects qml6-module-qt5compat-graphicaleffects qml6-module-qt-labs-folderlistmodel qml6-module-qt-labs-platform matugen jq dgop
```

## Step 3: Python Dependencies

```bash
pip install pynvml --break-system-packages
```

## Step 4: Install Fonts

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

### Noto Fonts (optional)

```bash
sudo apt install -y fonts-noto fonts-noto-color-emoji
```

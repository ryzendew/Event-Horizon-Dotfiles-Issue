# Features

Here's what's actually included in this setup. I've gone through the QML code to document what's really there, not just what sounds good.

## Core Components

### Window Manager

- **Hyprland** - Tiling Wayland compositor with animations and window management
- **Hardware acceleration** - GPU acceleration is enabled
- **Window rules** - You can customize how windows behave

### Shell System

- **Quickshell** - Qt-based shell with widgets, launchers, and desktop stuff
- **Modular** - Everything is split into components so you can customize it

## Desktop Components

### Top Bar

The top bar can be positioned at the top or bottom of the screen. It has three sections (left, center, right) where you can add widgets. Available widgets include:

- **App Launcher** - Quick access to application launcher
- **Workspace Switcher** - Shows current workspace and lets you switch
- **Focused Window** - Shows the title of the currently focused window
- **Running Apps** - Shows all running applications with focus indication
- **Clock** - Time and date display
- **Weather Widget** - Current weather conditions and temperature
- **Media Controls** - Control currently playing media (MPRIS)
- **Clipboard Manager** - Access clipboard history
- **CPU Usage** - CPU usage indicator (requires dgop)
- **Memory Usage** - Memory usage indicator (requires dgop)
- **CPU Temperature** - CPU temperature display (requires dgop)
- **GPU Temperature** - GPU temperature display (requires dgop, not recommended on laptops)
- **System Tray** - System notification area icons
- **Privacy Indicator** - Shows when microphone, camera, or screen sharing is active
- **Control Center Button** - Access to system controls
- **Notification Center Button** - Access to notifications
- **Battery** - Battery level and power management
- **VPN** - VPN status and quick connect
- **Idle Inhibitor** - Prevent screen timeout
- **Network Speed Monitor** - Network download/upload speed (requires dgop)
- **Keyboard Layout Name** - Shows active keyboard layout and allows switching
- **Notepad Button** - Quick access to notepad
- **Color Picker** - Quick access to color picker
- **System Update** - Check for system updates (Arch/Fedora only)
- **Dark Dash** - Quick access dashboard
- **Applications** - macOS Tahoe-style launcher

You can also add spacers and separators to organize widgets.

### Dock

A dock at the bottom of the screen (or top, depending on your config) with lots of customization options:

- **Pinned applications** - Pin your favorite apps
- **Running applications** - Shows currently running apps
- **Window previews** - Hover to see window previews
- **Group apps** - Option to group multiple windows of the same app
- **Auto-hide** - Hide the dock when not in use
- **Hide on games/apps** - Automatically hide when fullscreen apps are running
- **Expand to screen** - Expand dock to full width
- **Center apps** - Center the apps in the middle of the screen
- **Tooltips** - Show app names and window titles on hover
- **Widget areas** - Left and right widget areas with the same widgets available as the top bar
- **Customizable appearance** - Background tint opacity, widget area opacity, and more

### Control Center

System control panel with customizable widgets:

- **Night Mode** - Blue light filter toggle (if supported)
- **Dark Mode** - System theme toggle
- **Do Not Disturb** - Block notifications
- **Keep Awake** - Prevent screen timeout
- **Network** - Wi-Fi and Ethernet connection management
- **Bluetooth** - Device connections
- **Audio Output** - Speaker settings
- **Audio Input** - Microphone settings
- **Volume Slider** - Audio volume control
- **Brightness Slider** - Display brightness control
- **Input Volume Slider** - Microphone volume control
- **Battery** - Battery and power management
- **Performance** - Power and performance modes
- **Volume Mixer** - Per-application audio control
- **HDR Toggle** - Toggle HDR display settings

The control center has an edit mode where you can add, remove, and rearrange widgets.

### Application Launchers

Multiple launcher options:

- **Spotlight** - Main launcher with search, app categories, and keyboard navigation
- **Applications Popout** - macOS Tahoe-style launcher with categorized apps, suggested apps based on usage, and search
- **App Drawer** - Grid-based application browser
- **Fuzzel** - Fallback launcher (dmenu-style)
- **Anyrun** - Alternative fallback launcher

### Overview

Workspace overview mode that works across multiple screens:

- **All open windows** - Shows all windows on the current workspace
- **Workspace management** - Switch between workspaces
- **Window switching** - Click or keyboard navigate to switch windows
- **Screenshots** - Captures screenshots of windows for previews
- **Multi-screen support** - Works on all connected displays

### Dark Dash

A customizable dashboard with multiple tabs:

- **Overview Tab** - System overview with widgets
- **Media Player Tab** - Media player controls with album art
- **Weather Tab** - Weather information and forecasts

You can open it to specific tabs via IPC commands.

### Notepad

Built-in notepad with:

- **Multiple tabs** - Create and manage multiple notes
- **File support** - Open and save text files
- **Auto-save** - Automatically saves to session
- **Unsaved changes detection** - Warns before closing tabs with unsaved changes
- **Slideout panel** - Slides in from the side
- **Expandable** - Can expand to full width
- **Persistent storage** - Notes persist across sessions

## System Integration

### Audio

- **EasyEffects** - Audio effects and equalizer
- **Pavucontrol** - Volume control GUI
- **WirePlumber** - Audio session management
- **MPRIS** - Media player controls for any MPRIS-compatible player
- **Per-application volume** - Control volume for individual apps
- **Audio output switching** - Switch between audio devices
- **Input volume control** - Microphone volume control

### Display Management

- **Multi-monitor support** - Full support for multiple displays
- **Display configuration** - Configure each display independently
- **Night mode** - Blue light filter (if supported by your hardware)
- **HDR support** - HDR toggle and configuration
- **Brightness control** - Per-display brightness (if supported)
- **Color management** - HDR color profiles and settings

### Network Management

- **WiFi connections** - Connect to WiFi networks
- **Ethernet** - Ethernet connection management
- **VPN support** - VPN status and quick connect
- **Network info modal** - Detailed network information
- **Connection editing** - Edit saved connections
- **Network speed monitoring** - Real-time download/upload speeds (requires dgop)

### Power Management

- **Battery monitoring** - Battery level, charging status, time remaining
- **Power profiles** - Performance, balanced, power saving modes
- **Power menu** - Logout, suspend, hibernate, reboot, power off
- **Power confirmation** - Confirmation dialogs for power actions
- **Idle inhibitor** - Keep system awake when needed

### Bluetooth

- **Device management** - View and connect to Bluetooth devices
- **Quick connect** - Quick access to Bluetooth from control center
- **Device status** - Shows connected devices

## Utilities

### Screenshot Tools

- **Grim** - Takes screenshots
- **Slurp** - Lets you select a region
- **Swappy** - Edit screenshots
- **OCR support** - Tesseract integration for text recognition

### Clipboard Management

- **Cliphist integration** - Full clipboard history
- **Clipboard modal** - Browse and search clipboard history
- **Thumbnail support** - Shows thumbnails for images
- **Process tracking** - Shows which process copied each item
- **Keyboard navigation** - Navigate clipboard history with keyboard

### Color Picker

- **Hyprpicker integration** - System-wide color picker
- **Modal interface** - Easy access color picker modal
- **Quick access** - Available from top bar and dock

### File Management

- **File browser modal** - Built-in file browser
- **File info** - View file information
- **Keyboard navigation** - Navigate files with keyboard
- **Nautilus integration** - Also uses Nautilus file manager

### Terminal

- **Ptyxis** - Terminal emulator
- **Desktop terminal widget** - Terminal widget on desktop
- **Multiple instances** - Run multiple terminal windows

### Process Management

- **Process list modal** - View all running processes
- **Process list popout** - Full-screen process viewer
- **Performance tab** - CPU, memory, network usage
- **System tab** - System information
- **Process context menu** - Actions on processes
- **Kill processes** - Terminate processes from the UI

## Desktop Widgets

You can add widgets directly to your desktop:

- **CPU Temperature** - CPU temp display
- **GPU Temperature** - GPU temp display
- **System Monitor** - System resource monitor
- **Clock** - Desktop clock widget
- **Weather** - Weather widget
- **Terminal** - Desktop terminal
- **Dark Dash** - Desktop dashboard

All desktop widgets are positionable and can be enabled/disabled individually.

## Customization Features

### Theming

- **Material You** - Color scheme support via matugen
- **Dynamic color extraction** - Extracts colors from wallpapers
- **Custom themes** - Create and save custom themes
- **Built-in themes** - Several themes included
- **GTK theming** - GTK theme integration
- **Qt theming** - Qt theme integration
- **Theme colors tab** - Configure theme colors in settings

### Wallpapers

- **Wallpaper cycling** - Automatically cycle through wallpapers
- **Video wallpapers** - Support for video wallpapers
- **Wallpaper restoration** - Restores video wallpapers after reboot
- **Multiple sources** - Support for different wallpaper sources

### Visual Effects

- **Window blur** - Blur effects on windows and layers
- **Animations** - Smooth animations throughout
- **Custom shaders** - Shader effects available in hypr/shaders
- **Visual effects config** - Configure blur and other effects

### Keyboard Shortcuts

- **Comprehensive shortcuts** - Lots of keyboard shortcuts
- **Customizable keybinds** - Add your own keybinds
- **App-specific shortcuts** - Shortcuts for specific apps
- **Workspace navigation** - Keyboard workspace switching
- **Keybinds tab in settings** - View and configure all keybinds

### Settings

The settings modal has tons of configuration options:

- **Top Bar** - Configure top bar widgets and position
- **Dock** - Configure dock appearance and behavior
- **Desktop Widgets** - Configure desktop widgets
- **Display** - Display settings and configuration
- **Sound** - Audio settings
- **Network** - Network configuration
- **Bluetooth** - Bluetooth settings
- **Power** - Power management settings
- **Personalization** - Theme and appearance
- **Time** - Time and date settings
- **Weather** - Weather service configuration
- **Keyboard** - Keyboard layout and language
- **Default Apps** - Configure default applications
- **Window Sizing** - Window size and positioning
- **About** - System information

## Additional Features

### Notifications

- **Notification center** - Full notification center
- **Notification popups** - Popup notifications
- **Notification history** - View past notifications
- **Do not disturb** - Block notifications
- **Notification management** - Dismiss and manage notifications

### Lock Screen

- **Customizable lock screen** - Full lock screen customization
- **Security** - Password/PIN entry
- **Status information** - Shows system status on lock
- **Caps lock indicator** - Shows Caps Lock status
- **Keyboard** - On-screen keyboard support

### System Monitor

- **Mission Center integration** - System resource monitoring
- **CPU and memory** - Real-time usage display
- **Process management** - View and manage processes
- **System information** - Detailed system info

### System Updates

- **Update checking** - Check for system updates
- **Update popout** - View available updates
- **Distribution support** - Works on Arch and Fedora
- **Update notifications** - Notifies when updates are available

### Privacy

- **Privacy indicator** - Shows when mic/camera/screen sharing is active
- **Privacy service** - Tracks privacy-related activities
- **Privacy controls** - Manage privacy settings

### IPC (Inter-Process Communication)

You can control the shell via IPC commands:

- **Overview** - Open/close/toggle overview
- **Dark Dash** - Open/close/toggle dark dash (with tab selection)
- **Notepad** - Open/close/toggle notepad
- **App Drawer** - Open/close/toggle app drawer
- **Power Menu** - Open/close/toggle power menu
- **Process List** - Open/close/toggle process list
- **Spotlight** - Open/close/toggle spotlight

## Application Support

### Office Suite

- **WPS Office** - Office suite integration
- **Document editing** - Full document editing support

### Development Tools

- **Visual Studio Code** - Code editor integration
- **Zed** - Modern code editor
- **Gedit** - Text editor

### Browsers

- **Firefox** - Main browser
- **Google Chrome** - Also supported

## Scripts and Automation

### Custom Scripts

- **SSH agent management** - start-ssh-agent.sh
- **Video wallpaper restoration** - __restore_video_wallpaper.sh
- **Polkit testing** - test-polkit.sh
- **GTK theming** - gtk.sh
- **Qt theming** - qt.sh
- **Matugen worker** - matugen-worker.sh
- **NVIDIA GPU temp** - nvidia_gpu_temp.py
- **Gedit crash fix** - fix-gedit-crash.sh

### Automation

- **Startup scripts** - Executed on Hyprland startup
- **Background services** - Various background services
- **System integration** - Integration with system services

## Accessibility

- **On-screen keyboard** - Built-in on-screen keyboard
- **Keyboard navigation** - Full keyboard navigation support
- **Interface scaling** - Customizable interface scaling
- **Screen reader compatibility** - Works with screen readers where supported

## Performance

- **Hardware acceleration** - Full GPU acceleration
- **Optimized rendering** - Efficient rendering pipeline
- **Efficient resource usage** - Low resource footprint
- **Smooth animations** - 60fps animations

## Security

- **Polkit integration** - Privilege escalation via polkit
- **Secure sessions** - Secure session management
- **Privacy controls** - Privacy and security settings
- **System security** - Integration with system security features

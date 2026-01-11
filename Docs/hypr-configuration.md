# Hypr Configuration Guide

This explains how the `hypr` folder is organized and what all the config files do.

## Overview

The `hypr` folder has all the Hyprland config files. I've split everything into multiple files to make it easier to manage and customize.

## Main Configuration File

### `hyprland.conf`

This is the main file that loads all the other config files. It loads them in this order:

1. Monitor settings first (so they take priority)
2. Default configs from the `hyprland` folder
3. Custom configs from the `custom` folder (these override the defaults)

The file structure:

```
# Monitor settings (loaded first)
source=~/.config/hypr/monitors.conf

# Defaults from hyprland folder
source=~/.config/hypr/hyprland/env.conf
source=~/.config/hypr/hyprland/execs.conf
source=~/.config/hypr/hyprland/general.conf
source=~/.config/hypr/hyprland/rules.conf
source=~/.config/hypr/hyprland/keybinds.conf

# Custom overrides (loaded last)
source=~/.config/hypr/custom/env.conf
source=~/.config/hypr/custom/execs.conf
source=~/.config/hypr/custom/general.conf
source=~/.config/hypr/custom/rules.conf
source=~/.config/hypr/custom/keybinds.conf
```

## Configuration Folders

### `hyprland/` - Default Configuration

This folder has the default config files. Don't edit these directly - they might get overwritten if you update. Put your customizations in the `custom/` folder instead.

#### `hyprland/env.conf`

Environment variables and XWayland stuff:

- Desktop environment ID
- Wayland session config
- Qt and GTK settings
- App-specific env vars (for Firefox, Electron apps, etc.)
- Cursor size
- Polkit auth settings

#### `hyprland/execs.conf`

Stuff that runs when Hyprland starts:

- Desktop portal services
- Auth agents
- System services
- Background apps
- Polkit agents

#### `hyprland/general.conf`

General window manager settings:

- Input config (keyboard, touchpad)
- Rendering settings
- Window borders and gaps
- Layout config
- Animations
- Workspace setup

#### `hyprland/rules.conf`

Default window and layer rules:

- App-specific window rules
- Layer rules for special windows
- Window decoration rules
- Focus rules

#### `hyprland/keybinds.conf`

Default keyboard shortcuts:

- Window management
- Workspace navigation
- App launchers
- System controls
- Media controls

#### `hyprland/colors.conf`

Default color scheme.

### `custom/` - User Customization

This is where you put your customizations. **Edit files here, not in the `hyprland/` folder.**

#### `custom/env.conf`

Custom environment variables. Mostly empty right now, but add your own env vars here.

#### `custom/execs.conf`

Custom startup apps. Put anything you want to launch at startup here.

#### `custom/general.conf`

Custom general settings. Has some XWayland config. Add your own window manager settings here.

#### `custom/rules.conf`

Custom window and layer rules. This file has:

- Quickshell layer rules for blur
- Window rounding rules
- Focus rules for specific apps
- Sidebar config
- App-specific window rules

Add your own window rules here using Hyprland's window rules syntax.

#### `custom/keybinds.conf`

Custom keyboard shortcuts. Add your own keybinds here. It's empty right now, ready for you to add stuff.

#### `custom/scripts/`

Custom shell scripts:

- `__restore_video_wallpaper.sh` - Restores video wallpapers after reboot
- `start-ssh-agent.sh` - Starts SSH agent
- `test-polkit.sh` - Tests polkit auth

### `hyprland/scripts/`

Default scripts that come with the config:

- `fuzzel-emoji.sh` - Emoji picker
- `record.sh` - Screen recording
- `workspace_action.sh` - Workspace management
- `zoom.sh` - Zoom stuff

## Additional Configuration Files

### `monitors.conf`

Multi-monitor setup. This file has:

- Monitor outputs (DP-1, DP-2, DP-3, etc.)
- Resolution and refresh rate
- Monitor positioning
- Color management (HDR, color profiles)
- Brightness and saturation

**Important:** This loads first so monitor settings take priority. You'll need to edit this to match your monitors.

### `workspaces.conf`

Workspace config. Defines workspace names, bindings, and rules.

### `hypridle.conf` and `hypridle.conf.new`

Config for `hypridle` (idle daemon). Handles:

- Screen locking
- Display power management
- System suspend
- Idle timeouts

### `hyprlock.conf` and `hyprlock.conf.new`

Config for `hyprlock` (lock screen). Defines:

- Lock screen appearance
- Lock screen widgets
- Security settings

### `hyprlock/` Folder

Lock screen scripts:

- `check-capslock.sh` - Shows Caps Lock status
- `status.sh` - Shows system status on lock screen

### `shaders/` Folder

Custom shader effects:

- `chromatic_abberation.frag` - Chromatic aberration
- `crt.frag` - CRT monitor effect
- `drugs.frag` - Visual effect shader
- `extradark.frag` - Extra dark filter
- `invert.frag` - Color inversion
- `solarized.frag` - Solarized colors

You can apply these to windows or the whole screen.

### `hyprhdr.py`

Python script for HDR management. Handles HDR config and color management.

## Configuration Best Practices

### Making Customizations

1. **Always edit files in `custom/`** - Don't touch files in `hyprland/` directly, they might get overwritten
2. **Use the right file** - Match the setting type to the right config file
3. **Test your changes** - After editing, reload with `hyprctl reload` or restart Hyprland

### Adding New Keybinds

Add keybinds to `custom/keybinds.conf`. Use this syntax:

```bash
bind = MODIFIER, KEY, action, command
```

### Adding Window Rules

Add window rules to `custom/rules.conf`. These let you customize how apps behave:

```bash
windowrulev2 = PROPERTY, VALUE, class:^(APPLICATION)$
```

### Adding Startup Applications

Add startup apps to `custom/execs.conf`:

```bash
exec-once = application-name
```

### Monitor Configuration

Edit `monitors.conf` to match your displays. Use `hyprctl monitors` to see what your monitor outputs are called.

## File Locations

When you install this, copy the `hypr` folder to:

```
~/.config/hypr/
```

So you end up with this structure:

```
~/.config/hypr/
├── hyprland.conf
├── monitors.conf
├── workspaces.conf
├── hypridle.conf
├── hyprlock.conf
├── hyprland/
│   ├── env.conf
│   ├── execs.conf
│   ├── general.conf
│   ├── rules.conf
│   ├── keybinds.conf
│   ├── colors.conf
│   └── scripts/
├── custom/
│   ├── env.conf
│   ├── execs.conf
│   ├── general.conf
│   ├── rules.conf
│   ├── keybinds.conf
│   └── scripts/
├── hyprlock/
├── shaders/
└── hyprhdr.py
```

## Reloading Configuration

After you make changes, reload Hyprland:

```bash
hyprctl reload
```

Or just log out and back in to restart everything.

## Additional Resources

- [Hyprland Wiki](https://wiki.hyprland.org/) - Official docs
- [Hyprland Configuration](https://wiki.hyprland.org/Configuring/Variables/) - Config variable reference
- [Window Rules](https://wiki.hyprland.org/Configuring/Window-Rules/) - Window rules docs
- [Keybinds](https://wiki.hyprland.org/Configuring/Binds/) - Keybinding reference


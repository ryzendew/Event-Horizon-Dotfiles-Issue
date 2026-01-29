# How to Report an Issue or Bug

Thank you for taking the time to report an issue! To help us understand and resolve your problem quickly, please follow this guide when creating a bug report.

---

## Title / Short Summary

Provide a clear, one-line description of your issue.

**Good examples:**
- `Window floating breaks after monitor hotplug`
- `Hyprlock crashes on login with NVIDIA GPU`
- `Keybind Super+S not switching workspaces`

**Bad examples:**
- `It doesn't work`
- `Bug`
- `Help me please`

---

## Distro & Version

Include your distribution name, version, kernel version, and desktop environment.

```bash
# Example output to include:
Distro: Arch Linux
Kernel: 6.12.1-arch1-1
Desktop: Hyprland (Wayland)
```

---

## Hardware / Environment

Provide details about your hardware setup:

```bash
# Example:
CPU: AMD Ryzen 7 5800X
GPU: NVIDIA RTX 3080 (Driver: 550.107.02)
RAM: 32GB
Type: Desktop
```

---

## What I Tried

List the commands, configurations, or packages you installed before the issue occurred. Be specific about any changes you made:

- Commands run
- Config files edited
- Packages installed
- System changes

```bash
# Example:
sudo pacman -S hyprland
# Edited ~/.config/hypr/hyprland.conf
# Installed nwg-look from AUR
```

---

## Exact Error Messages

Copy and paste the **full** error messages, logs, or include screenshots. Use code blocks for readability:

```bash
# Example error format:
[ERROR]2024-01-15 10:30:45] [hyprland] Caught signal 11 (SIGSEGV)
#0: Hyprland(_Z15getCleanupJobsv+0x29c7c) [0x...]
#1: linux上的sigaction()+0x [...]
```

> 💡 **Tip:** For terminal output, use triple backticks with the language identifier (e.g., ```bash).

---

## Expected vs Actual Behavior

Clearly describe what you expected to happen versus what actually happened:

**Expected:**
> Describe what should have happened

**Actual:**
> Describe what actually happened

```text
# Example:
Expected: Window should float when pressing Super+F
Actual: Window freezes and Hyprland crashes with signal 11
```

---

## Optional: System Info / Logs

Include relevant system information and logs to help diagnose the issue:

### Inxi Output
```bash
inxi -F
```

### Journalctl Logs
```bash
journalctl --no-pager -b 0 | tail -n 100
```

### Hyprland Logs
```bash
# Check for Hyprland crash logs
cat ~/.cache/hyprland/hyprland.log

# Or run Hyprland with verbose logging
Hyprland -v
```

### Dmesg (for hardware issues)
```bash
dmesg | tail -n 50
```

---

## Quick Checklist Before Submitting

- [ ] Search existing issues to avoid duplicates
- [ ] Tested with default configurations (if applicable)
- [ ] Included all required sections above
- [ ] Used clear, descriptive title
- [ ] Added error messages in code blocks
- [ ] Verified the issue is reproducible

---

## Additional Tips

1. **Search first:** Check if your issue has already been reported
2. **Minimal reproduction:** Try to isolate the issue to the smallest set of steps
3. **Update first:** Ensure you're running the latest versions
4. **Test defaults:** Temporarily reset configs to rule out configuration issues

---

Thank you for helping make this project better! 🙏

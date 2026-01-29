---
name: Bug Report
description: Report a bug or issue
labels: bug
body:

  - type: input
    id: title
    attributes:
      label: Title / Short Summary
      description: A clear, one-line description of your issue
      placeholder: e.g., "Window floating breaks after monitor hotplug"
    validations:
      required: true

  - type: textarea
    id: distro
    attributes:
      label: Distro & Version
      description: Your distribution name, version, kernel version, and desktop environment
      placeholder: |
        Distro: [e.g., Arch Linux]
        Kernel: [e.g., 6.12.1-arch1-1]
        Desktop: [e.g., Hyprland (Wayland)]
    validations:
      required: true

  - type: textarea
    id: hardware
    attributes:
      label: Hardware / Environment
      description: CPU, GPU, RAM, laptop/desktop, etc.
      placeholder: |
        CPU: [e.g., AMD Ryzen 7 5800X]
        GPU: [e.g., NVIDIA RTX 3080 (Driver: 550.107.02)]
        RAM: [e.g., 32GB]
        Type: [e.g., Desktop]
    validations:
      required: true

  - type: textarea
    id: what-i-tried
    attributes:
      label: What I Tried
      description: List commands, configs, packages you installed, edits you made
      placeholder: |
        - [e.g., Ran `sudo pacman -S hyprland`]
        - [e.g., Edited `~/.config/hypr/hyprland.conf`]
        - [e.g., Installed package from AUR]
    validations:
      required: true

  - type: textarea
    id: error-messages
    attributes:
      label: Exact Error Messages
      description: Copy-paste full errors, logs, or describe what happened
      render: bash
      placeholder: |
        ```bash
        [Paste your error messages here]
        ```
    validations:
      required: true

  - type: textarea
    id: expected-actual
    attributes:
      label: Expected vs Actual Behavior
      description: What you expected vs what actually happened
      placeholder: |
        **Expected:**
        > [What you expected]

        **Actual:**
        > [What actually happened]
    validations:
      required: true

  - type: textarea
    id: system-info
    attributes:
      label: Optional: System Info / Logs
      description: Output of inxi -F, journalctl -xe, dmesg | tail, etc.
      render: bash
      placeholder: |
        ```bash
        # inxi -F
        [Paste inxi output here]

        # journalctl --no-pager -b 0 | tail -n 100
        [Paste journalctl output here]

        # dmesg | tail -n 50
        [Paste dmesg output here]
        ```

  - type: checkboxes
    id: checklist
    attributes:
      label: Checklist
      description: Confirm you've done the following
      options:
        - label: Searched existing issues to avoid duplicates
        - label: Tested with default configurations (if applicable)
        - label: Issue is reproducible
        - label: Included all relevant information above

---

## Quick Tips

- **Good title:** "Window floating breaks after monitor hotplug"
- **Bad title:** "It doesn't work", "Bug", "Help me please"
- Use code blocks (```bash) for terminal output and errors
- Be specific about what you were doing when the issue occurred

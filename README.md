
# My NixOS Configuration

This repository contains my personal configuration files for NixOS and bash:

- `configuration.nix`: Main system configuration for NixOS.
- `.bashrc`: Bash initialization script for interactive non-login shells.
- `.bash_profile`: Bash initialization script for login shells.

## 🧠 Important Notes Before Use

### ⚠️ Read Before Applying
Please **read and understand the `configuration.nix`** file **before using it** on your system. It includes several system-level changes that may not be suitable for your setup out of the box.

---

## 📝 Customization Required

- **Username**: Make sure to replace any hardcoded usernames with your own in the configuration.
- **VMware Users**: If you're running NixOS inside VMware, there's a command in the config for enabling VMware tools. It is currently **commented out** — **uncomment it** if you're using VMware.
- **Font Customization**: The config already includes options to set custom fonts.
- **Unwanted GNOME Apps**: The config removes some default GNOME apps to keep your system lean. if u want u can also add some of the app or remove it.Its ups to you

---

## 🐚 Bash Setup in NixOS

To enable `~/.bash_profile` on NixOS:

1. Create both `.bashrc` and `.bash_profile` in your home directory.
2. Make sure `.bash_profile` sources `.bashrc` like this:

    ```bash
    if [ -f ~/.bashrc ]; then
        . ~/.bashrc
    fi
    ```

This ensures both login and non-login shells are properly configured.

---

## 📁 Files Overview

- `configuration.nix`: System-wide configuration. Handles desktop settings, packages, services, and more.
- `.bashrc`: Sets environment variables, aliases, and other shell preferences.
- `.bash_profile`: Loads `.bashrc` during login.

---

## ⚙️ How to Use

1. Fork or clone this repo.
2. Modify `configuration.nix` to fit your system:
   - Change the username.
   - Uncomment VMware tools command if applicable.
3. Copy `.bashrc` and `.bash_profile` to your home directory.
4. Rebuild your NixOS system with:

    ```bash
    sudo nixos-rebuild switch
    ```

---

## 💬 Final Reminder

**Do not use this configuration without understanding it.** It may change system-level behavior. Review each section of `configuration.nix` carefully.

---

Happy hacking! ⚡

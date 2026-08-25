# Framework Penguin

Plymouth Boot Screen for Framework

![Framework Penguin Animation](penguin-anim.gif)

A custom Plymouth boot screen theme featuring Framework's ASCII-art penguin animation.

This version includes LUKS disk encryption password entry UI based on the original bgrt default login (lock icon, entry box, and bullet characters for password masking).

## Credits

Animation sourced from Framework's ASCII penguin motion graphic.

## Installation

### Prerequisites

This theme uses Plymouth's **script** module, so you need the script plugin as well as Plymouth itself.

**Fedora/RHEL:**
```bash
sudo dnf install plymouth plymouth-scripts plymouth-plugin-script
```

> Fedora ships the script plugin in its own package.

**Debian/Ubuntu:**
```bash
sudo apt install plymouth plymouth-themes
```

**Arch Linux:**
```bash
sudo pacman -S plymouth
```

### Install the Theme

1. Copy the theme to Plymouth's themes directory:
   ```bash
   sudo cp -r framework-penguin /usr/share/plymouth/themes/
   ```

2. Set the theme as default:
   ```bash
   sudo plymouth-set-default-theme -R framework-penguin
   ```

## Distro Logo

The default logo is fedora, but you can insert any logo by replacing the `watermark.png` image.

## Animation

Plymouth's refresh callback fires at roughly 50Hz, so `framework-penguin.script` advances
the animation by `throbber_speed = 0.5` frames per refresh to play back at close to the
source's native 24fps. Raise or lower `throbber_speed` to speed up or slow down the loop.

## License

The theme code — `framework-penguin.script` and `framework-penguin.plymouth` — is
[MIT](LICENSE) licensed.

The bundled images are **not**. The penguin animation frames are Framework's artwork,
the password-entry icons come from Plymouth's `spinner` theme under GPL-2.0-or-later,
and `watermark.png` is a Fedora trademark. See [LICENSES.md](LICENSES.md) for the
per-file breakdown.

# Tilix


[Tilix](https://gnunn1.github.io/tilix-web/) is an advanced GTK3 tiling terminal emulator.

<!--more-->

## Installation

- apt
  ```bash
  sudo apt install tilix
  [[ -x $(command -v nautilus) ]] && sudo apt install python-nautilus
  ```
- pacman
  ```bash
  sudo pacman -S tilix
  [[ -x $(command -v nautilus) ]] && sudo pacman -S python-nautilus
  ```

## Set `tilix` as the default GUI terminal emulator

- Ubuntu: `sudo update-alternatives --config x-terminal-emulator`
- Arch and derivatives:  Select `tilix` in `Prefered applications`.


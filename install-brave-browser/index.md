# Install Brave browser


[Brave](https://brave.com/) is a Chromium-based web browser focused on speed, privacy, (and crypto).

<!--more-->

## Ubuntu / PoPOS

```bash
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main" | sudo tee /etc/apt/sources.list.d/brave-browser-release.list
sudo apt update &&  sudo apt install brave-browser
```

## Arch-based

Via [AUR](https://aur.archlinux.org/packages/brave-bin/)

```bash
paru -S brave-bin
```

## Windows

Via [chocolatey](https://community.chocolatey.org/packages/brave)

```bash
choco install brave
```


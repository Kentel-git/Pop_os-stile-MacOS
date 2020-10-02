# Make Linux Look Like MacOS - GNOME Desktop Environment

This Project is to make Ubuntu and other derivitive distributions (Mint, PopOS, etc.) look like MacOS. *Version 20+ is required*

_Source Files in this project_
- https://www.gnome-look.org/p/1148692/ - Capitine Cursors
- https://www.pling.com/p/1403328/ - WhiteSur GTK Theme
- https://www.pling.com/p/1399044/ - BigSur Icon Theme
- https://github.com/PRATAP-KUMAR/focalgdm3 - Login Theme
- https://albertlauncher.github.io/docs/installing/ - Albert
- https://www.pling.com/p/1401527/ - Cairo Dock

## Installation

### Dependancy Installs

```bash
sudo apt install gnome-tweak-tool gnome-shell-extensions chrome-gnome-shell -y
```

### Gnome Extensions

Enable Extensions by visiting https://extensions.gnome.org/ install add-on and reload browser

Install the Following Extensions
- User Themes
- Frippery Move Clock
- Dynamic Panel Transparency
- Compiz Windows Effect
- Panel OSD

### Gnome Tweaks

```bash
gsettings set org.gnome.mutter center-new-windows 'true'
gsettings set org.gnome.desktop.wm.preferences button-layout 'close,minimize,maximize:'
```

### Manual Extension Configurations

Panel OSD - Change Horizonal and Vertical to 98

### Albert

```bash
curl https://build.opensuse.org/projects/home:manuelschneid3r/public_key | sudo apt-key add -
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_20.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo wget -nv https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_20.04/Release.key -O "/etc/apt/trusted.gpg.d/home:manuelschneid3r.asc"
sudo apt update
sudo apt install albert
```

### Change Login Screen

```bash
wget -qO - https://github.com/PRATAP-KUMAR/focalgdm3/archive/master.tar.gz | tar zx --strip-components=1 focalgdm3-master/focalgdm3
```


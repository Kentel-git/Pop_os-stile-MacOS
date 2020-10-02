# Make Linux Look Like MacOS - GNOME Desktop Environment

This Project is to make Ubuntu and other derivative distributions (Mint, PopOS, etc.) look like MacOS. *Version 20+ is required*

_Source Files in this project_
- https://www.gnome-look.org/p/1148692/ - Capitine Cursors
- https://www.pling.com/p/1403328/ - WhiteSur GTK Theme
- https://www.pling.com/p/1399044/ - BigSur Icon Theme
- https://github.com/PRATAP-KUMAR/focalgdm3 - Login Theme
- https://albertlauncher.github.io/docs/installing/ - Albert
- https://www.pling.com/p/1401527/ - Cairo Dock

## Installation

### Dependency Installs

```bash
sudo apt install git gnome-tweak-tool gnome-shell-extensions chrome-gnome-shell cairo-dock -y
git clone https://github.com/ChrisTitusTech/Linux-MacOS-GNOME.git ~/MacOS
mkdir ~/.themes
mkdir ~/.icons
mv ~/MacOS/themes/* ~/.themes
mv ~/MacOS/icons/* ~/.icons
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
gsettings set org.gnome.desktop.interface gtk-theme "WhiteSur-dark"
gsettings set org.gnome.desktop.wm.preferences theme "WhiteSur-dark"
gsettings set org.gnome.desktop.interface icon-theme 'BigSur'
gsettings set org.gnome.desktop.interface cursor-theme 'capitaine-cursors-light'
gsettings set org.gnome.desktop.background picture-uri 'file:///~/MacOS/walls/macOS-BS3.jpg'
```

### Manual Extension Configurations

- Panel OSD - Change Horizontal and Vertical to 98
- Cairo Dock - Set to Startup Applications
- Cairo Dock Themes - Import all gz files to Cairo configure in ~/MacOS/cairo
- Cairo Dock Configure - Turn of Icon effects and animations and hide dock when overlapping windows
- Cairo Dock Launchpad - Add Custom Launchpad Shortcut `dbus-send --session --type=method_call --dest=org.gnome.Shell /org/gnome/Shell org.gnome.Shell.Eval string:'Main.shellDBusService.ShowApplications();'`
- Disable Ubuntu Dock (Not Needed on PopOS)
- Dynamic Panel Transparency - Background Tab - Max Opacity 100 - Min Opacity 50

### Albert

```bash
curl https://build.opensuse.org/projects/home:manuelschneid3r/public_key | sudo apt-key add -
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_20.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo wget -nv https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_20.04/Release.key -O "/etc/apt/trusted.gpg.d/home:manuelschneid3r.asc"
sudo apt update
sudo apt install albert -y
```

- Launch Albert
- Set Hotkey - Meta + F
- Set Theme Arc Dark Blue
- Enable Albert Extensions


### Change Login Screen

```bash
cd ~/MacOS
wget https://raw.githubusercontent.com/PRATAP-KUMAR/focalgdm3/TrailRun/focalgdm3
chmod +x focalgdm3
sudo ./focalgdm3 ~/MacOS/walls/macOS-BS1.jpg
```


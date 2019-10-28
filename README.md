# Sway-Pop Setup WIP

### Enable Wayland
```sudo nano /etc/gdm3/custom.conf```

Comment out `#WaylandEnable=false`

### Install sway
```sudo apt install sway swayidle swaylock rofi```

### Install Font Awesome 5
```
wget https://use.fontawesome.com/releases/v5.11.2/fontawesome-free-5.11.2-desktop.zip
unzip fontawesome-free-5.11.2-desktop.zip
sudo mkdir /usr/share/fonts/truetype/font-awesome/
sudo cp fontawesome-free-5.11.2-desktop/otfs/Font\ Awesome\ 5\ Free-Regular-400.otf /usr/share/fonts/truetype/font-awesome/font-awesome-free-regular.otf
sudo cp fontawesome-free-5.11.2-desktop/otfs/Font\ Awesome\ 5\ Free-Solid-900.otf /usr/share/fonts/truetype/font-awesome/font-awesome-free-solid.otf
```

### Install light
```
wget https://github.com/haikarainen/light/releases/download/v1.2/light_1.2_amd64.deb
sudo dpkg -i light_1.2_amd64.deb
```

Add your user to the video group
```sudo usermod -a -G video username```

### Install dependencies
```
sudo apt install meson cmake pkg-config wayland-protocols libwayland-dev libcairo2-dev \
libpango1.0-dev libsystemd-dev libgdk-pixbuf2.0-dev scdoc libinput-dev libgtkmm-3.0-dev \
libdbusmenu-gtk3-dev libjsoncpp-dev libnl-3-dev libnl-genl-3-dev libpulse-dev libmpdclient-dev \
libboost-program-options-dev libboost-dev libpulse-dev grim slurp
```

### Install wob
```
git clone git@github.com:WatchMkr/wob.git
cd wob
git clone git@github.com:swaywm/wlr-protocols.git
meson build-release --buildtype release
ninja -C build-release
sudo ninja -C build-release install
```

### Install mako
```
git clone git@github.com:WatchMkr/mako.git
cd mako
meson build
sudo ninja -C build install
```

### Install Waybar
```
git clone https://github.com/WatchMkr/Waybar.git
cd Waybar
meson build
sudo ninja -C build install
```

### Install pamixer
git clone https://github.com/WatchMkr/pamixer.git
cd pamixer
make
sudo make install

### Install config
```
git clone git@github.com:WatchMkr/sway.git
cd sway
mkdir ~/.config/mako
mkdir ~/.config/rofi
mkdir ~/.config/sway
mkdir ~/.config/waybar
ln -sr .config/rofi/* ~/.config/mako/
ln -sr .config/rofi/* ~/.config/rofi/
ln -sr .config/sway/* ~/.config/sway/
ln -sr .config/waybar/* ~/.config/waybar/
```

# Minimalist Arch Linux with i3-wm and Brave Browser

# Archinstaller
```sh
# Zero drive; first get drive like "nvme0n1"
lsblk -o NAME,SIZE,MODEL
dd if=/dev/urandom of=/dev/nvme0n1 bs=4M

# Install arch instller keyring fix
pacman -Sy archlinux-keyring
archinstall
```

# Setup
```sh
# Utilities (wifi, clipboard, less)
sudo pacman -S iwd xclip less
# Coding
sudo pacman -S git code
```

# Install Brave Browser
```sh
sudo pacman -S --needed base-devel
sudo git clone https://aur.archlinux.org/yay.git
sudo chown -R  $USER:users yay
cd yay
makepkg -si
yay -S brave
```

# Fix resolution by lowering DPI
```sh ~/.Xresources
Xft.dpi: 220
xterm*faceName: DejaVu Sans Mono:size=20
xterm*background: #2E3440
xterm*foreground: #D8DEE9
```

# Audio via HDMI
- First list your sinks `pactl list sinks`
- Find the HDMI and set it `pactl set-default-sink <sink-index>`


# VSCode
If pasting doesn't work, remove keybindings
- press CTRL+K then CTRL+S
- search for "paste" and remove the 2 bindings (CTRL+V and CTRL+Insert)

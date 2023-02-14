# Install Hyprland on Arch Linux 

## Step 1:
Download Arch Linux from the offical Arch website https://archlinux.org/download/

## Step 2: 
Install Arch Linux using archinstall command [archinstall](https://wiki.archlinux.org/title/archinstall#:~:text=archinstall%20is%20a%20helper%20library,the%20official%20documentation%20for%20that.)

## Step 3:
Intialize pacman keys and populate Arch Linux
```
sudo pacman-keys --init
```
```
sudo pacman-keys --populate archlinux
```

## Step 4:
Clone the GIT Repository
```
git clone https://github.com/kshitijdhara/Arch-hyprland
``` 
## Step 5:
Provide executeable permissions for all scripts
```
cd Arch-hyprland
sudo chmod +x *.sh
``` 
## Step 6:
Install yay
```
./install-yay.sh
```
or
```
git clone https://aur.archlinux.org/yay-bin
cd yay-bin
makepkg -si
```
## Step 7:
Install essential packages
```
./ctt-install.sh
```
or 
```
./install.sh
```
## Step 8:
Copy config files to relevant directories
```
mkdir .wallpapers
cp Arch-hyprland/dotfiles/.config .config
cp Arch-hyprland/wall.jpg .wallpapers
```
## Step 9:
Check hypr/hyprland.conf and make changes based on installed packages for example terminal used might wezterm so change the keybinding from kitty to wezterm.
Also set appropriate path to wallpaper
## Step 10:
Add these lines to your .bashrc
```
# Log WLR errors and logs to the hyprland log. Recommended
export HYPRLAND_LOG_WLR=1

# Tell XWayland to use a cursor theme
export XCURSOR_THEME=Bibata-Modern-Classic

# Set a cursor size
export XCURSOR_SIZE=24

# Example IME Support: fcitx
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
export SDL_IM_MODULE=fcitx
export GLFW_IM_MODULE=ibus
```
##  Step 11:
Check if Hyprland works 
Run the following as non-root user
```
Hyprland
```
If everything works fine continue else refer Hyprland wiki [install](https://wiki.hyprland.org/Getting-Started/Installation/) and [master tutorial](https://wiki.hyprland.org/Getting-Started/Master-Tutorial) 
## Step 12:
Enable SDDM Service
```
sudo systemctl enable sddm.service
```
## Step 13:
Reboot system and login through SDDM. If you are stuck in a loop and cannot login to Hyprland. Press CRTL+ALT+F2/F3 to move to TTY and check the issues.
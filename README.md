# dotfiles

<img src="https://github.com/josemapt/dotfiles/blob/main/screenshots/qtile.jpg">

***Quick Links***
  - [Qtile](https://github.com/josemapt/dotfiles/tree/main/.config/qtile)

# Base pakages:

```
base base-devel linux linux-firmware neovim intel-ucode networkmanager
```


# Pakages to download first:
```
sudo pacman -S xorg xorg-server xorg-xinit qtile firefox alacritty
```
Then start qtile and copy the rest.

# Rest of pakages:
```
sudo pacman -S thunar nitrogen python dmenu picom brightnessctl git alsa-utils python-psutil acpi dunst exa unzip volumeicon cbatticon network-manager-applet udiskie ntfs-3g glib2 gvfs geeqie libreoffice tk xf86-video-intel xcb-util-cursor scrot redshift xdotool
```

# Installing yay.
```
git clone https://aur.archlinux.org/yay.git

cd yay

makepkg -si
```

# Whith yay:
```
yay -S vscodium-bin nerd-fonts-ubuntu-mono ccat
```

# Clone 

# Finally set execution permission to this scripts:
```
chmod +x scripts/*.sh
chmod +x scripts/*.py
chmod +x .config/qtile/autostart.sh
```


<br>
<hr>
<br>

# Solving screen tearing problem in firefox:
Type <b>about:config</b> and set <b>layers.acceleration.force-enabled = true</b>

<br>
<hr>
<br>

# Changing GTK theme:
Download any theme in https://www.gnome-look.org/browse/cat/135/ord/rating/ and run:
```
cd Downloads/
tar -xf THEME.tar.gz
sudo mv THEME /usr/share/themes
```
Download the <b>breeze</b> cursor theme in https://www.gnome-look.org/p/999927/ and run:
```
cd Downloads/
tar -xf 165371-Breeze.tar.gz
rm 165371-Breeze.tar.gz
sudo mv Breeze /usr/share/icons
```
Now edit <b>~/.config/gtk-3.0/settings.ini</b> and <b>/usr/share/icons/default/index.theme</b> by adding these lines:
```
# ~/.config/gtk-3.0/settings.ini
[Settings]
gtk-icon-theme-name = ICON THEME
gtk-theme-name = THEME
gtk-cursor-theme-name = Breeze

# /usr/share/icons/default/index.theme
[Icon Theme]
Inherits=Breeze
```
And reboot

<br>
<hr>
<br>

# Changing lightdm theme:
Run:
```
sudo pacman -S lightdm-webkit2-greeter
yay -S lightdm-webkit-theme-aether

systemctl enable lightdm
```
And reboot


<br>
<hr>
<br>

# Changing GRUB theme
Download <b>vimix</b> grub theme from https://www.gnome-look.org/browse/cat/109/ord/rating/ and run:
```
cd Downloads/
tar -xf Vimix-1080p.tar.xz
rm Vimix-1080p.tar.xz
sudo mv Vimix-1080p /boot/grub/themes
```
Then edit <b>/etc/default/grub</b> by uncomment <b>GRUB_THEME</b> and add:
```
GRUB_THEME="/boot/grub/themes/Vimix-1080p/Vimix/theme.txt"
```
And applay changes:
```
sudo su
grub-mkcongif -o /boot/grub/grub.cfg
```
If everything goes right then you'll see:
```
Found theme: /boot/grub/themes/Vimix-1080p/Vimix/theme.txt
```

<br>
<hr>
<br>

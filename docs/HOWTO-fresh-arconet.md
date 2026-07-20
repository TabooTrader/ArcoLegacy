# Fresh Arconet / Arch setup with ArcoLegacy helpers

## After first boot

1. Update the system
   sudo pacman -Syu

2. Install base tools
   sudo pacman -S git base-devel paru

3. Copy helper scripts to ~/bin
   mkdir -p ~/bin
   cp /path/to/ArcoLegacy/scripts/*.sh ~/bin/
   chmod +x ~/bin/*.sh
   echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc

4. Optional: install post-install packages
   # Review packages/packages-post-install.txt first
   paru -S firefox betterbird arc-gtk-theme bibata-cursor-theme \
     xfce4-whiskermenu-plugin htop btop timeshift pavucontrol \
     network-manager-applet blueman noto-fonts

5. XLibre (if desired)
   # Add [xlibre] repo to /etc/pacman.conf (see configs/pacman.conf)
   # Import and sign the key, then:
   sudo pacman -Syyu xlibre-xserver xlibre-input-libinput

6. Classic ATT (optional)
   # Restore att-old from WD backups, then use tools/ README launcher

## Kernel reminder

Stay on regular linux unless you have a strong reason to switch.
Avoid linux-zen on this hardware for now.

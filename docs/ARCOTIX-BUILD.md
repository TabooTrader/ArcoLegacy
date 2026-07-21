# ARCOTIX build status

Last reviewed: 2026-07-21

## Location

/run/media/bigf/WD-Project/ARCOTIX/build-workspace/ARCOTIX/

## Profile summary

- iso_name / publisher: ARCOTIX
- install_dir: arcotix
- bootmodes: uefi.grub only
- Init target: Artix s6 (s6, s6-rc, s6-linux-init + *-s6 service packages)
- Desktop: XFCE + SDDM
- Kernel: linux + linux-headers (not zen)

## packages.x86_64 notes

Keep for ISO:
- base, linux, firmware, artix-keyring
- s6 stack + elogind-s6, networkmanager-s6, sddm-s6, bluez-s6, cups-s6
- xfce4, xfce4-goodies, sddm, grub, efibootmgr
- pipewire stack, networkmanager, bluez
- sudo, nano, vim, git, base-devel, reflector, mkinitcpio

Likely build-breakers (move to post-install later):
- paru
- icecat
- onlyoffice
- betterbird

Missing candidate:
- mkinitcpio-archiso (if building with archiso)

## pacman.conf

Artix: system / world / galaxy via mirrorlist-artix
Also: xlibre, chaotic-aur

Build host must provide:
- /etc/pacman.d/mirrorlist-artix
- chaotic-mirrorlist + keys if chaotic packages are kept

## Next steps (priority)

1. Slim packages.x86_64 for a reliable first ISO (drop AUR-heavy apps)
2. Confirm archiso vs artools build command on this tree
3. Clean old work/ out/ if permissions block rebuild
4. Test boot in VM before real hardware
5. Installer strategy later (Calamares or manual + post-script)

## Related

ArcoLinuXR (Arconet + script) remains the fast daily-driver path.
ARCOTIX remains the Artix s6 long-term goal.

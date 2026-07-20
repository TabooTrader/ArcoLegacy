# ArcoLegacy / ARCOTIX Decisions

## Kernel
- Prefer regular `linux` + `linux-headers`
- Avoid linux-zen and other high-performance kernels (linked to blackout/logout issues on this hardware)

## Init / Distro base
- Target: Artix s6 when installer cooperates
- Daily driver fallback: Arconet / Arch-based with systemd until Artix large-drive issues are solved
- Prefer GRUB over systemd-boot

## Display
- XLibre over stock Xorg when available
- SDDM preferred display manager
- XFCE 4.x desktop

## Audio
- PipeWire stack (pipewire, wireplumber, pipewire-pulse, pipewire-alsa, pipewire-jack)

## Packaging philosophy
- Keep ISO package list light
- Use scripts / post-install lists for extras
- Avoid unnecessary Rust-heavy core replacements where practical
- Preserve classic ArcoLinux look (Arc theme, Sardi icons, familiar XFCE layout)

## Repos of interest
- XLibre: https://packages.xlibre.net/arch/stable/$arch
- nemesis_repo (local or GitHub mirror)
- chaotic-aur (optional, use carefully)

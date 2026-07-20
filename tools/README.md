# Tools

Helpers related to Arch Linux Tweak Tool (ATT) and other utilities.

## ATT notes

The classic (old) ATT lives in backups as att-old / archlinux-tweak-tool-master.

Common issues on fresh installs:
- Permission denied on /tmp/att.pid  → create it owned by your user
- Gtk.Screen is None               → run under a real X session, not pure TTY
- Root config paths                 → do not launch ATT with sudo

## Suggested launcher (user-level)

Save as ~/bin/old-att and chmod +x:

#!/bin/bash
# Launch classic ATT from the backed-up tree
ATT_ROOT="$HOME/att-old/archlinux-tweak-tool-master"
PIDFILE="/tmp/att.pid"

# Ensure pid file is writable by the user
if [ ! -f "$PIDFILE" ]; then
  touch "$PIDFILE" 2>/dev/null || sudo touch "$PIDFILE"
  sudo chown "$USER:$USER" "$PIDFILE" 2>/dev/null
fi

cd "$ATT_ROOT" || exit 1
exec python3 usr/share/archlinux-tweak-tool/archlinux-tweak-tool.py

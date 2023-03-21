---
title: "CryoUtilities Offline Installation"
date: "2023-03-21"
draft: false
toc: false
images:
tags:
  - tutorial
  - cryoutilities
---

This quick guide is intended to allow firewalled countries to install CU2.

**NOTE:** This method won't let you update or uninstall normally since you'll need an internet connection for those. However, it WILL allow you to use CU2 as normal.

1. Download ![this file with the necessary code](/CU-Offline-Install.zip) to your Steam Deck/Device.
2. Open Konsole and use the following commands, pressing the Enter/Return key after each:

```bash
cd
mkdir .cryo_utilities
cd .cryo_utilities
```

3. Move `cryo_utilities`, `icon.png` and `launcher.sh` from `CU-Offline-Install.zip` to `~/.cryo_utilities`.
4. Open Konsole and paste the entire block below, then press Enter/Return:

```bash
cd ~/.cryo_utilities
chmod +x cryo_utilities
chmod +x launcher.sh
xdg-icon-resource install cryo-utilities.png --size 64
echo "#!/usr/bin/env xdg-open
[Desktop Entry]
Name=CryoUtilities
Exec=bash $HOME/.cryo_utilities/launcher.sh
Icon=cryo-utilities
Terminal=false
Type=Application
StartupNotify=false" >"$HOME"/Desktop/CryoUtilities.desktop
chmod +x "$HOME"/Desktop/CryoUtilities.desktop
echo "#!/usr/bin/env xdg-open
[Desktop Entry]
Name=CryoUtilities
Exec=bash $HOME/.cryo_utilities/launcher.sh
Icon=cryo-utilities
Terminal=false
Type=Application
Categories=Utility
StartupNotify=false" >"$HOME"/.local/share/applications/CryoUtilities.desktop
chmod +x "$HOME"/.local/share/applications/CryoUtilities.desktop
update-desktop-database ~/.local/share/applications
```
Now, you should be all set to use CryoUtilities as normal!

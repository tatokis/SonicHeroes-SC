A simple dinput8.dll proxy that remaps the Steam Controller in Sonic Heroes to fix the rotating camera bug when ran in wine (proton), as well as the button mapping.
This is a fork of https://github.com/MrColdbird/SW42-SteamGamepadFix

# Usage

## Linux

Copy dinput8.dll from the binaries folder to the game's installation directory (same place as Tsonic_win.exe).
Identify the proton/wine prefix directory and run winecfg in it. For example:

```
WINEPREFIX="/home/user/.steam/steamapps/compatdata/NNNNNNNNNN/pfx/" winecfg
```

Under libraries, add a new override for "dinput8", and set it to `native` only. Click OK.
Next, go to proton's dll path and add a symlink for dinput8base.dll.so. (Newer wine versions may only have dll files. This was tested against Proton 4.2.)

```
cd ~/.steam/compatibilitytools.d/Proton_4.2_noesync/dist/lib/wine
ln -s dinput8.dll.so dinput8base.dll.so
```

## Windows (untested)

Copy dinput8.dll from the system directory to the game's installation directory (same place as Tsonic_win.exe).
The system directory is C:\Windows\SysWoW64 for 64 bit Windows, and C:\Windows\System32 for 32 bit.
Rename the copied file (in the game directory) to dinput8base.dll

Copy dinput8.dll from the binaries folder in this repository to the game's installation directory (same place as Tsonic_win.exe).

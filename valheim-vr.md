# Valheim VR on Linux

I managed to get this working on SteamVR, but not through OpenComposite.

Sadly, SteamVR on Linux has major performance issues, so VHVR is not exactly enjoyable.

## Download files
- BepInExPack: https://thunderstore.io/c/valheim/p/denikson/BepInExPack_Valheim/
- VHVR mod: https://github.com/brandonmousseau/vhvr-mod/releases

## Installation

### Start by unzipping the BepInEx zip and cd into its main folder
```bash 
unzip denikson-BepInExPack_Valheim-*.zip
cd BepInExPack_Valheim
```

### Unzip VHVR on top
```bash
unzip ../vhvr-*.zip
```

### Fix case mismatch between mod and game (or else it will crash on startup)
```bash
mv `Valheim_Data` `valheim_Data`
```

### Replace openvr_api.dll with the OpenComposite one
```bash
cp ../openvr_api.dll valheim_Data/Plugins/x86_64/openvr_api.dll
```

### Install to your Valheim game folder
```bash
cp -r ./* ~/.steam/root/steamapps/common/Valheim
```

## Launching

Native Linux version will not work with VHVR, so we will need to use Proton.

**Recommended Proton**: GE-Proton9-16

**Launch Options**: `WINEDLLOVERRIDES="winhttp=n,b" %command%`

Start the mode in the default mode (no Vulkan/OpenGL/etc)

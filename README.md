# Sonic Unleashed Recompiled - Linux ARM64 Wrapper
This wrapper is made for retro handhelds to run Unleashed Recompiled. The binary needed to run the game is not included and must be built--see [BUILDING.md](https://github.com/JeodC/PortMaster-UnleashedRecomp/blob/main/unleashedrecomp/BUILDING.md). You must also provide your own game files.

## Installation
The recomp installer does not support a headless window system and will crash on trying to open a file browser window to locate game assets. After installing this wrapper, you must install the game files from a desktop installation. The folder structure has been created for convenience--simply copy the *same* folders from your desktop installation to `ports/unleashedrecomp`.

## Settings Recommendations
On arm64 handhelds, the port runs best with low res shadows and 30-60fps with bilinear filtering. On the Retroid Pocket Mini, setting internal resolution to 50% (640x480) will increase stability.

## Mods
Mods will work without HedgeModManager, but require manual installation and setup. In your `ports/unleashedrecomp/mods` folder you'll find a file `ModDB.ini`. Open it and modify it:

```ini
[Main]
ManifestVersion=1.1
ReverseLoadOrder=0
ActiveMod0=Miku
ActiveModCount=1
FavoriteModCount=0

[Mods]
Miku="./mods/Hatsune Miku/mod.ini"

[Codes]
Code0="DisableAutoSaveWarning"
Code1="FixUnleashOutOfControlDrain"
Code2="FixEggmanlandUsingEventGalleryTransition"
Code3="HomingAttackOnJump"
CodeCount=4
```

You can disable the codes as you wish. After copying your mod to the `mods` folder, edit the `ModDB.ini` file to point to the mod's own `mod.ini` file by following the above example. Don't forget to increment `ActiveModCount` as you add more mods. Some mods can crash the port--if you run into crashes, try disabling mods one by one until you find the culprit.

## Thanks
Sega -- The game  
hedge-dev -- The recomp  
고우키 -- First alert for an arm64 build's existence  
Cyril Deletre -- Build steps  
# Overview

This is a compatibility patch between the Machine Shipset and Gigastructural Engineering & More (3.6) to allow regular ringworld sections to use the Machine Shipset graphics (including the Hive and Machine variants) for regular-sized ringworlds.  For larger flavors of ringworlds, you will need [Machine Shipset Add-on: Gigastructural Engineering Ringworlds - Titanic, Behemoth, and Gargantuan](https://steamcommunity.com/sharedfiles/filedetails/?id=2644469566) which is a separate, optional mod due to the graphical oddities created by the unaltered Machine Shipset ringworld graphics being reused in unintended ways.

Combined with my other mods Ringworld Graphical Enhancements and Machine Shipset Add-on: Shattered Ring Appearance, your Origin: Shattered Ring empires will again have the correct Machine Shipset graphics for their starting ringworlds.

# Changes

Adds graphical entities for the Machine Shipset that are compatible with the ringworld changes from Gigastructural Engineering & More (3.6).  Adds an event to assign the `machine_01` graphical culture to ringworld megastructures if the constructing empire has that graphical culture.

Also replaces two graphical entities from base Gigas - `giga_ringworld_3x_seams_entity` and `giga_ringworld_destroyed_entity` - to support alternative mesh usage for custom ringworlds.  Instead of having the central ringworld section's mesh be a part of entity, all 3 sections are added as attachments.  This allows each attached entity to use the mesh defined for its graphical culture.  Basically, without this change the central part of ringworlds under construction wouldn't match correctly.

## Compatibility

Same compatibility as Gigastructural Engineering & More (3.6).

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements, but neither are the dependencies.

### Required Dependency Mods

* [Machine Shipset](https://steamcommunity.com/sharedfiles/filedetails/?id=2077186491) for the original graphics and other ship-related code
* [Gigastructural Engineering & More (3.6)](https://steamcommunity.com/sharedfiles/filedetails/?id=1121692237) is the mod we're making compatible

### Recommended Companion Mods

* [Ringworld Graphical Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2628518102) to apply the owner's graphical culture to the ringworld from Origin: Shattered Ring (my mod Subtle Polish is not recommended due to a high likelihood of conflicts with Gigas)
* [Machine Shipset Add-on: Shattered Ring Appearance](https://steamcommunity.com/sharedfiles/filedetails/?id=2628980994) ensures that the permanently-destroyed sections for Origin: Shattered Ring using the Machine Shipset properly display as that shipset (adds missing graphical definitions to the Machine Shipset)
* [Machine Shipset Add-on: Gigastructural Engineering Ringworlds - Titanic, Behemoth, and Gargantuan](https://steamcommunity.com/sharedfiles/filedetails/?id=2644469566) to enable the Machine Shipset graphics for all three additional sizes of ringworlds added by Gigastructural Engineering - warning: the graphics were not edited to reduce curvature, so it produces fairly bendy-looking rings

### When to Install

This mod can be safely added after the game has started, but should not be removed from a game in-progress.  It can theoretically be removed from a game in progress - any standard ringworlds should will likely revert to the fallback appearance for the Machine Shipset (`mammalian_01`), except for the special Origin: Shattered Ring starting section.  Back up your savegame before attempting to remove a mod.

### Known Issues

In order to apply the graphics from the Machine Shipset for ringworlds to Gigas, it was necessary to overwrite two of its entity definitions (text files which tell the game how to attach models and textures, and how to shade them).  Overriding a graphics entity causes an error log - expect two entries similar to these:

```
[23:42:04][graphics/pdx_entity.cpp:2546]: Duplicate of giga_ringworld_3x_seams_entity added to entity system
[23:42:04][graphics/pdx_entity.cpp:2546]: Duplicate of giga_ringworld_destroyed_entity added to entity system
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Mark as compatible with Stellaris version 3.2 "Herbert" - no script changes
* 1.2.0 Mark as compatible with Stellaris version 3.3 "Libra" - no script changes
* 1.3.0 Mark as compatible with Stellaris version 3.4 "Cepheus" - no script changes
* 1.4.0 Mark as compatible with Stellaris version 3.6 "Orion"
    * Add support for Machine dyson spheres for class O stars (including the destroyed variant)
* 1.5.0 Add support for many additional megastructures from Gigastructural Engineering & More
    * Add compatibility trigger for other mods to check whether this one is active

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/machine_shipset_gigastructures_ringworld_compatibility)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.
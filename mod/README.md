# Overview

This is a compatibility patch between the Machine Shipset and Gigastructural Engineering & More (3.1) to allow regular ringworld sections to use the Machine Shipset graphics (including the Hive and machine variants) for regular-sized ringworlds.  Not yet tested with the larger flavors of ringworld.

Combined with my other mods Ringworld Graphical Enhancements and Machine Shipset Add-on: Shattered Ring Appearance, your Origin: Shattered Ring empires will again have the correct Machine Shipset graphics for their starting ringworlds.

# Changes

Adds graphical entities for the Machine Shipset that are compatible with the ringworld changes from Gigastructural Engineering & More (3.1).  Adds an event to assign the `machine_01` graphical culture to ringworld megastructures if the constructing empire has that graphical culture.

Also replaces two graphical entities from base Gigas - `giga_ringworld_3x_seams_entity` and `giga_ringworld_destroyed_entity` - to support alternative mesh usage for custom ringworlds.  Instead of having the central ringworld section's mesh be a part of entity, all 3 sections are added as attachments.  This allows each attached entity to use the mesh defined for its graphical culture.  Basically, without this change the central part of ringworlds under construction wouldn't match correctly.

## Compatibility

Same compatibility as Gigastructural Engineering & More (3.1).

Built for Stellaris version 3.1.\* "Lem."  Not compatible with achievements.

### Required Dependency Mods

[Machine Shipset](https://steamcommunity.com/sharedfiles/filedetails/?id=2077186491) for the original graphics and other ship-related code.

[Gigastructural Engineering & More (3.1)](https://steamcommunity.com/sharedfiles/filedetails/?id=1121692237) is the mod we're making compatible.

### Recommended Companion Mods

[Ringworld Graphical Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2628518102) to apply the owner's graphical culture to the ringworld from Origin: Shattered Ring.  Using my mod Subtle Polish is not recommended due to a high likelihood of conflicts with Gigas.

[Machine Shipset Add-on: Shattered Ring Appearance](https://steamcommunity.com/sharedfiles/filedetails/?id=2628980994) ensures that the permanently-destroyed sections for Origin: Shattered Ring using the Machine Shipset properly display as that shipset.  This mod adds missing graphical definitions to the Machine Shipset.

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub]()

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.
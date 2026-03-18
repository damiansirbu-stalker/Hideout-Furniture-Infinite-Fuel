Hideout-Furniture-Infinite-Fuel-DAMIAN
======================================

Author: Damian (patch)
Original: Hideout Furniture by Aoldri
Date: 2025-12-12

PURPOSE
-------
Removes fuel/battery consumption from all placeable light furniture.
Lights no longer require batteries, kerosene, or gauss ammo to operate.

AFFECTED ITEMS
--------------
- Metal Torch (was: batteries_dead, 800h)
- Gas Lamp (was: kerosene, 1200h)
- Gas Lamp GAMMA variant (was: kerosene, 99999h)
- Light Altar (was: ammo_gauss, 2400h)

All other furniture (workshop, radio, displays, stashes) do not consume
fuel and are unaffected.

TECHNICAL CHANGE
----------------
File: gamedata/scripts/bind_light_furniture.script
Line 88 (in placeable_light_wrapper:__init):

Original:
    self.infinite_fuel = data and data.is_world_obj

Modified:
    self.infinite_fuel = true

This forces ALL placeable lights to have infinite fuel, regardless of
whether they are world objects or player-placed items.

DEPENDENCIES
------------
REQUIRED: Hideout Furniture by Aoldri (provides bind_hf_base.script)
This mod extends bind_hf_base.hf_binder_wrapper class.

INSTALLATION
------------
1. Place this mod folder in D:\GAMMA\mods\
2. Enable in MO2
3. Ensure this mod loads AFTER:
   - 245- Hideout Furniture - Aoldri (REQUIRED)
   - SixSloth's & Veerserif's Hideout Furnitures 2.2.1 GAMMA patch
   - G.A.M.M.A. Light Sources Spawner

COMPATIBILITY
-------------
This is a simple file replacement (not DLTX).
Overrides: bind_light_furniture.script

Works with:
- Hideout Furniture by Aoldri
- SixSloth's & Veerserif's Hideout Furnitures
- Even More Hideout Furnitures
- Hideout Furniture Expansion
- G.A.M.M.A. Light Sources Spawner

PRESERVED FUNCTIONALITY
-----------------------
- Light on/off toggle
- Flickering during emissions and near psi mutants
- Sound effects (turn on, turn off, humming)
- Particles (gas lamp flame)
- Bone visibility changes
- All visual effects

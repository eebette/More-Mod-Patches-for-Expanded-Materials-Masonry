# More Mod Patches for Expanded Materials - Masonry

[![Latest Release](https://img.shields.io/github/v/release/eebette/More-Mod-Patches-for-Expanded-Materials-Masonry?label=Latest%20Release)](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Masonry/releases)
<!-- Steam Workshop badge goes here at publish -->

![Expanded Materials - Masonry: Mod Patches](Media/Badge_MMMas.png)

A bunch of unofficial mod patches for [Expanded Materials - Masonry][emmas]. I did my best to match that author's
conventions.

[emmas]: https://steamcommunity.com/sharedfiles/filedetails/?id=3662913084

## Coverage

| Concrete goes on | Examples | EMMas param |
|---|---|---|
| **Conventional turrets & artillery** | MG/autocannon emplacements, field guns, mortars, howitzers | 25% / factor 2 |
| **Civil power plants** | magma-thermal, geothermal, steam, nuclear generators | 25% / factor 2 |
| **Heavy extraction / bio rigs** | core drills, bone drills | 25% / factor 2 |
| **Automated factory machinery** | concrete pad under the metal chassis | 25% / factor 2.5 |

24 buildings across 5 mods:

<details><summary>Combat Extended Armory (12)</summary>

- `CE_Turret_12PounderBombard` - 12-pounder bombard
- `CE_Turret_GatlingGun` - Gatling gun
- `CE_Turret_M1919Browning` - M1919 machine gun
- `CE_Turret_M2HB` - M2 Browning machine gun
- `CE_Turret_MkNineteenGL` - Mk 19 grenade launcher
- `CE_Turret_OrganGun` - organ gun
- `CE_Turret_PKM` - PKM machine gun
- `CE_Turret_PortableMortar` - 60mm portable mortar
- `CE_Turret_SPGNine` - SPG-9 recoilless gun
- `CE_Turret_ShotgunTurret` - shotgun auto-turret
- `CE_Turret_TwelvePounder` - 12-pounder cannon
- `CE_Turret_Vickers` - Vickers machine gun

</details>

<details><summary>Combat Extended Guns (1)</summary>

- `CE_Artillery_Howitzer` - 105mm howitzer

</details>

<details><summary>Alpha Biomes (5)</summary>

- `AB_Turret_Propane` - propane turret
- `AB_MagmaThermalPlant` - magma-thermal generator
- `AB_MagmaThermalPlant_Advanced` - advanced magma-thermal generator
- `AB_CoreSampleDrill` - core sample drill
- `AB_BoneDistillery` - bone drill

</details>

<details><summary>Vanilla Quests Expanded - The Generator (5)</summary>

- `VQE_AncientGeothermalGenetron` - ancient geothermal ARC
- `VQE_Genetron_Geothermal` - geothermal ARC
- `VQE_Genetron_ThermalVent` - thermal-vent ARC
- `VQE_Genetron_SteamPowered` - steam-powered ARC
- `VQE_Genetron_Nuclear` - nuclear ARC

</details>

<details><summary>Vanilla Quests Expanded - Drone Factory (1)</summary>

- `VFEFactory_DroneAutofactory` - drone autofactory (concrete pad; also TemperedSteel from the Metals patch)

</details>

## Load order

> RimWorld -> Argonic Core -> Expanded Materials - Masonry -> this mod -> Metals mod patches.

Requires [Argonic Core](https://steamcommunity.com/sharedfiles/filedetails/?id=2944251509) and
[Expanded Materials - Masonry][emmas]; load it **after** EMMas and **before**
[More Mod Patches for Expanded Materials - Metals](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals)
(if you run it).

## My other mods

### The CE + Simple Sidearms suite

<table>
<tr><th width="300">Module</th><th width="540">What it does</th></tr>
<tr><td width="300"><a href="https://github.com/eebette/CombatExtended-SimpleSidearms-Compatibility-Patch"><img src="Media/Badge_Patch.png" width="300" alt="CE + Simple Sidearms Compatibility Patch"></a></td><td width="540">Core compatibility patch for Combat Extended and Simple Sidearms.</td></tr>
<tr><td width="300"><a href="https://github.com/eebette/CombatExtended-SimpleSidearms-Compatibility-Loadouts"><img src="Media/Badge_Loadouts.png" width="300" alt="CE + Simple Sidearms Loadouts Module"></a></td><td width="540">Syncs loadouts between Combat Extended and Simple Sidearms.</td></tr>
<tr><td width="300"><a href="https://github.com/eebette/CombatExtended-SimpleSidearms-Compatibility-Tactics"><img src="Media/Badge_Tactics.png" width="300" alt="Compatibility Module - Tactics"></a></td><td width="540">Sensible tweaks to nonsense pawn behavior when CE + SS run together.</td></tr>
</table>

### Expanded Materials patches

<table>
<tr><th width="300">Mod</th><th width="540">What it does</th></tr>
<tr><td width="300"><a href="https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals"><img src="Media/Badge_MMP.png" width="300" alt="Expanded Materials - Metals: Mod Patches"></a></td><td width="540">Extends Expanded Materials - Metals to support additional mods.</td></tr>
</table>

### Standalone

<table>
<tr><th width="300">Mod</th><th width="540">What it does</th></tr>
<tr><td width="300"><a href="https://github.com/eebette/Better-Attack-Orders-for-Simple-Sidearms"><img src="Media/Badge_BAO.png" width="300" alt="Better Attack Orders for Simple Sidearms"></a></td><td width="540">Adds sidearm attack orders to the right-click target menu.</td></tr>
<tr><td width="300"><a href="https://github.com/eebette/Pawns-Optimize-Weapon-Quality"><img src="Media/Badge_POWQ.png" width="300" alt="Pawns Optimize Weapon Quality"></a></td><td width="540">Pawns will upgrade their held guns when a higher-quality copy is available.</td></tr>
</table>

## FAQ

**CE compatible?**

Yes. **Load this after CE.**

**Can I add or remove it mid-save?**

Yep.

**Does it change balance?**

Not really. 

**AI?**

This mod was engineered with the help of an AI Coding Assistant (Claude Code, Fable 5, Max effort). The amount of
researching and deep-diving the compatibility interfaces of mods that it patches would have been insurmountable without
it.

Development followed a standard process driven and scrutinized by me (the real human person writing this):
explore, design, build, test, fix, review, scrutinize, test again over many rounds.

I have manually reviewed and verified all code in this mod.

I ask that if you have unconstructive feedback regarding the usage of AI while developing this mod, that it remains
outside of this community space. Thank you.

## Credit

[Argon][emmas], for some really awesome mods.

## License

[MIT](LICENSE)

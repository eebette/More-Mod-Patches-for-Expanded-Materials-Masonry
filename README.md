# More Mod Patches for Expanded Materials - Masonry

[![Latest Release](https://img.shields.io/github/v/release/eebette/More-Mod-Patches-for-Expanded-Materials-Masonry?label=Latest%20Release)](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Masonry/releases)
<!-- Steam Workshop badge goes here at publish -->

![Expanded Materials - Masonry: Mod Patches](Media/Badge_MMMas.png)

A companion patch for [Expanded Materials - Masonry][emmas] (EMMas). EMMas ships curated `ModPatches` that give a
**concrete** component to heavy, conventional, civil-scale buildings; this extends that same treatment to **modded
Steel-costing buildings EMMas does not cover**, so more of a heavy modlist's turrets, power plants and rigs are poured
partly from cement instead of pure Steel.

[emmas]: https://steamcommunity.com/sharedfiles/filedetails/?id=3662913084

## How it works

It reuses EMMas's own `ArgonicCore.PatchOperations.PatchOperationDistributeCost` with EMMas's own parameter - **25% of a
building's `Steel` cost becomes `EM_CementMix`** (`extraCostFactor 2`) - so its ops are indistinguishable in form and
numbers from EMMas's hand-written ones. A building gets concrete when the author would build it from concrete:

> a mounted conventional gun sits on a concrete emplacement; a civil power plant has a concrete foundation; a heavy
> extraction rig or bio-processor is a poured structure. Sleek energy/precision/reactor tech stays metal (that is the
> [Metals patch](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals)'s job).

Which buildings are concrete is read off EMMas's own roster - see [Methodology](#methodology) - and audited by an
independent adversarial pass.

## What it covers

| Concrete goes on | Examples | EMMas param |
|---|---|---|
| **Conventional turrets & artillery** | MG/autocannon emplacements, field guns, mortars, howitzers | 25% / factor 2 |
| **Civil power plants** | magma-thermal, geothermal, steam, nuclear generators | 25% / factor 2 |
| **Heavy extraction / bio rigs** | core drills, bone drills | 25% / factor 2 |
| **Automated factory machinery** | concrete pad under the metal chassis | 25% / factor 2 |

Only the building's `Steel` is drawn from; other costs are left untouched. On the factory machine that also gets metal,
the [Metals patch](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals) takes its TemperedSteel
share first and cement takes 25% of the remainder - the author's metals-first order.

## Covered buildings

37 buildings across 5 mods. Each mod has its own `IfModActive`-gated folder, so only the mods you actually run are
touched. Expand for the exact defs:

<details><summary>Combat Extended Armory (24)</summary>

- `CE_Turret_12PounderBombard` / `Turret_12PounderBombard` - 12-pounder bombard
- `CE_Turret_GatlingGun` / `Turret_GatlingGun` - Gatling gun
- `CE_Turret_M1919Browning` / `Turret_M1919Browning` - M1919 machine gun
- `CE_Turret_M2HB` / `Turret_M2HB` - M2 Browning machine gun
- `CE_Turret_MkNineteenGL` / `Turret_MkNineteenGL` - Mk 19 grenade launcher
- `CE_Turret_OrganGun` / `Turret_OrganGun` - organ gun
- `CE_Turret_PKM` / `Turret_PKM` - PKM machine gun
- `CE_Turret_PortableMortar` / `Turret_PortableMortar` - 60mm portable mortar
- `CE_Turret_SPGNine` / `Turret_SPGNine` - SPG-9 recoilless gun
- `CE_Turret_ShotgunTurret` / `Turret_ShotgunTurret` - shotgun auto-turret
- `CE_Turret_TwelvePounder` / `Turret_TwelvePounder` - 12-pounder cannon
- `CE_Turret_Vickers` / `Turret_Vickers` - Vickers machine gun

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

`PS_DeepchemRefinery` and `VCHE_DeepchemPumpjack` are concrete too, but **EMMas already cements them itself**, so this
patch leaves them alone (the Metals patch drops their metal so the author's cement is not starved).

## Load order

> RimWorld -> Argonic Core -> Expanded Materials - Masonry -> Metals mod patches -> this mod.

Requires [Argonic Core](https://steamcommunity.com/sharedfiles/filedetails/?id=2944251509) and
[Expanded Materials - Masonry][emmas]; load it **after** EMMas, and after
[More Mod Patches for Expanded Materials - Metals](https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals)
if you run it, so metal is drawn before cement.

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
<tr><td width="300"><a href="https://github.com/eebette/More-Mod-Patches-for-Expanded-Materials-Metals"><img src="Media/Badge_MMP.png" width="300" alt="Expanded Materials - Metals: Mod Patches"></a></td><td width="540">The metals sibling of this patch - extends Expanded Materials - Metals to support additional mods.</td></tr>
</table>

### Standalone

<table>
<tr><th width="300">Mod</th><th width="540">What it does</th></tr>
<tr><td width="300"><a href="https://github.com/eebette/Better-Attack-Orders-for-Simple-Sidearms"><img src="Media/Badge_BAO.png" width="300" alt="Better Attack Orders for Simple Sidearms"></a></td><td width="540">Adds sidearm attack orders to the right-click target menu.</td></tr>
<tr><td width="300"><a href="https://github.com/eebette/Pawns-Optimize-Weapon-Quality"><img src="Media/Badge_POWQ.png" width="300" alt="Pawns Optimize Weapon Quality"></a></td><td width="540">Pawns will upgrade their held guns when a higher-quality copy is available.</td></tr>
</table>

## FAQ

**CE compatible?**

Yes - it only touches building costs, nothing CE does.

**Can I add or remove it mid-save?**

Yep.

**Does it change balance?**

Slightly, in the same direction EMMas already goes: covered buildings cost some concrete instead of part of their Steel.
Wealth stays comparable.

**AI?**

This mod was engineered with the help of an AI Coding Assistant (Claude Code, Fable 5, Max effort). The amount of
researching and deep-diving the compatibility interfaces of mods that it patches would have been insurmountable without
it.

Development followed a standard process driven and scrutinized by me (the real human person writing this):
explore, design, build, test, fix, review, scrutinize, test again over many rounds.

I have manually reviewed and verified all code in this mod.

I ask that if you have unconstructive feedback regarding the usage of AI while developing this mod, that it remains
outside of this community space. Thank you.

## Methodology

Which buildings get concrete follows EMMas's own choices, not a rule invented here:

- EMMas cements conventional turrets (autocannon / minigun / siege emplacements), civil power plants
  (watermill / tidal / geothermal / nuclear), deep-extraction rigs (pumpjack / helixien pump) and heavy standalone
  bio/mech chambers - and pointedly does **not** cement energy weapons, reactors, doors, walls or radiation shielding
  (those it keeps metal; radiation shielding it always expresses as Lead). The modded buildings here are matched to
  those buckets by kind.
- An independent adversarial review (`tools/adversary-review.md`) re-derived EMMas's full cement + metal rosters from
  its XML and challenged every assignment; it also flagged and corrected metal-side mistakes in the sibling Metals
  patch (conventional turrets/generators that had been metal are now concrete; industrial machinery moved from Titanium
  to the author's TemperedSteel).
- `EM_CementMix` at 25% / factor 2 is EMMas's own standard; nothing here uses an invented number.

## Structure

Laid out like EMMas's own `ModPatches/` - one folder per patched mod under `ModPatches/1.6/<Mod>/Patches/`, each gated in
`LoadFolders.xml` by `IfModActive="<packageId>"`. Each folder's patch file has a **unique** name
(`<Mod>_Patch_Masonry.xml`): RimWorld's `LoadFolders` overrides files by relative path, so a shared filename across
folders would collapse to one and silently shadow the rest.

To cover another mod, add `ModPatches/1.6/<Mod>/Patches/<Mod>_Patch_Masonry.xml` and one `IfModActive="<packageId>"`
line in `LoadFolders.xml`. `tools/assignments.tsv` and `tools/adversary-review.md` record which building got concrete,
and why.

## Credit

The concrete-vs-metal conventions and the parameter here are [Argon's][emmas], inferred from EMMas's own patches and
extended to content they could not have covered. Bugs in the extension are mine.

## License

[MIT](LICENSE) - code, docs, and the badge artwork (the ingot and stone-block emblems are original; nothing here derives
from Combat Extended's art).

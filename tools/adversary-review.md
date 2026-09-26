# Adversarial review — EMM-Masonry companion first-pass

Independent red-team of `masonry-firstpass.tsv` against the author's actual
EMM-Metals (`3333419387`) + EMM-Masonry (`3662913084`) patches. I re-derived the
author's *complete* cement roster and metal roster from the XML rather than
trusting the first-pass notes.

## Author's actual cement roster (ground truth, all `EM_CementMix`)
| bucket | defs | % |
|---|---|---|
| Conventional turrets | VFES_Turret_AutocannonDouble/Minigun/AntiAir, VFES_LargeRepulsor | 25 |
| Conventional turrets (heavy) | VFES_Turret_Concealed, VFES_ConcealedBarrier | 75 |
| Siege engines | VFED_Turret_Kontarion/Palintone/Onager | 25 |
| Civil power plants | VFE_AdvancedWatermillGenerator, VPE_AdvancedGeothermalGenerator, VPE_NuclearGenerator, VFE_TidalGenerator | 25 |
| Deep extraction | PS_DeepchemRefinery, VCHE_DeepchemPumpjack, VHGE_HelixienPump | 25 |
| Heavy standalone bio/mech chambers | MechGestator, LargeMechGestator, BasicRecharger, StandardRecharger, GR_GenePod, VFEP_WarcasketFoundry | 25 |
| Factory automation (**BOTH** — also TemperedSteel 50/75%) | all 18 VFEFactory_* machines | 25 |
| Civil structure | Light_Streetlamp; VFEArch_ConcreteFoundation (repl); Asphalt (100) | 25/100 |

Decisive negatives for arbitration: **no door, no reactor core, no wall/shield, no
"DU"/radiation structure is ever cemented.** The only wall-like cement target is
`VFES_ConcealedBarrier` (a plain steel security barrier). Radiation shielding in
this mod family is always expressed as **EM_Lead (a metal)**, never concrete.

Author's metal palette (matters for cohesion): **Titanium** = ship/space/energy/
reactor/precision (reactors, laser/plasma/charge turrets, gravship engines,
astrofuel/solar generators). **TemperedSteel** = industrial *automation machinery*
(all VFEFactory_* machines, vehicles). **Lead** = batteries + radiation. Titanium
is NOT the author's metal for mundane production benches — TemperedSteel is.

## Per-building verdicts

| defName | my verdict | vs first-pass | reason (author analog) |
|---|---|---|---|
| PPCRailgun | metal | AGREE | railgun energy weapon = VFES_ChargeRailgun / ShipTurret_Laser → Titanium, no cement |
| AA_HexagelCoreReactor | metal | AGREE | reactor = Ship_Reactor → Titanium-only, no cement (could gain Lead like nuclear, minor) |
| CE_Turret_GatlingGun | cement | AGREE | conventional MG emplacement = VFES_Turret_Minigun (cement, never metaled by author) |
| CE_Turret_M1919Browning | cement | AGREE | conventional MG = VFES_Minigun class |
| CE_Turret_M2HB | cement | AGREE | conventional MG = VFES_AutocannonDouble class |
| CE_Turret_MkNineteenGL | cement | AGREE | autocannon/GL emplacement = VFES_AutocannonDouble |
| CE_Turret_PKM | cement | AGREE | conventional MG |
| CE_Turret_ShotgunTurret | cement | AGREE | conventional emplacement (has power/silicon; author's cemented turrets are also powered — pure cement still faithful) |
| CE_Turret_Vickers | cement | AGREE | conventional MG |
| CE_Turret_12PounderBombard | cement | AGREE | bombard = VFED_Onager siege class |
| CE_Turret_TwelvePounder | cement | AGREE | field cannon = siege class |
| CE_Turret_OrganGun | cement | AGREE | volley gun = siege class |
| CE_Turret_PortableMortar | cement | AGREE | mortar = siege class |
| CE_Turret_SPGNine | cement | AGREE | recoilless emplacement = conventional |
| Turret_* (12 non-CE twins) | cement | AGREE | identical defs, identical treatment |
| CE_Artillery_Howitzer | cement | AGREE | artillery = VFED siege class |
| AB_Turret_Propane | cement | AGREE | mounted flame turret = conventional emplacement (not energy/charge) |
| AB_MagmaThermalPlant | cement | AGREE | civil thermal plant = VPE_AdvancedGeothermalGenerator |
| AB_MagmaThermalPlant_Advanced | cement | AGREE | civil thermal plant |
| VQE_AncientGeothermalGenetron | cement | AGREE | geothermal = VPE_AdvancedGeothermalGenerator |
| VQE_Genetron_Geothermal | cement | AGREE | geothermal plant |
| VQE_Genetron_ThermalVent | cement | AGREE | thermal-vent plant = geothermal class |
| VQE_Genetron_SteamPowered | cement | AGREE (low conf) | big steam/boiler hall = civil plant; no exact author analog |
| VQE_Genetron_Nuclear | cement | AGREE | nuclear plant = VPE_NuclearGenerator (author cements it, drops Lead) |
| PS_DeepchemRefinery | cement (defer) | AGREE | author cements this exact def — MMP MUST drop its Titanium or it stacks metal+cement |
| VCHE_DeepchemPumpjack | cement (defer) | AGREE | author cements this exact def — same drop-metal fix |
| AB_CoreSampleDrill | cement | AGREE | standalone extraction rig = VCHE_DeepchemPumpjack (cement-only) |
| AB_BoneDistillery | cement | AGREE (reason fix) | heavy standalone bio-processor = GR_GenePod/MechGestator (cement-only) — NOT a "deep-extraction drill" |
| AB_PropaneSmelter | both | AGREE (caveat) | smelter = VFEFactory_AutomatedSmelter (both); metal should be TemperedSteel not Titanium |
| AB_PropaneTableMachining | both | AGREE (caveat) | machining = VFEFactory_AutomatedMachiningBay (both); TemperedSteel |
| AB_SlimeCompressor | both | AGREE | carries AdvancedResourceProcessor (factory-automation signature) → both |
| TableRimatomicsMachining | both | AGREE (caveat) | machining bench = AutomatedMachiningBay; TemperedSteel |
| RTC_EngineHanger | both | CHALLENGE→metal | passive Facility hangar frame, no processor/automation comp; author cemented no bare structural frame |
| RT_AssemblyBench | both | AGREE (caveat) | assembly = VFEFactory_AutomatedAssembler (both); TemperedSteel |
| RT_AssemblyCrane | both | CHALLENGE→metal | steel gantry crane (no power, no processor); no author "both" analog for a bare crane |
| VFE_ComponentFabricationBench | both | AGREE (caveat) | fab/assembly = VFEFactory_AutomatedAssembler; TemperedSteel |
| VFE_FueledSmelter | both | AGREE (caveat) | smelter = VFEFactory_AutomatedSmelter; but author left *plain* smelters metal-only |
| VFE_TableMachiningLarge | both | AGREE (caveat) | machining = AutomatedMachiningBay; author left plain machining tables metal-only |
| VFEFactory_DroneAutofactory | both | AGREE (strong) | literally a VFEFactory_* machine → unimpeachable both |

## Arbitrations (the 3 AMBIG)

**PlutoniumProcessor → METAL (keep Titanium+Lead, NO cement).** It is precision
nuclear-fuel processing kit carrying Lead radiation shielding, in the
reactor/refinery family the author metals (Ship_Reactor, VGE_CompactRefinery,
VGE_MechanoidResourceProcessor — all Titanium/Aluminium metal). The author cements
nuclear *generators* (power plants) and deep-*extraction* rigs; a fuel processor is
neither. Cement would misread reactor-hall precision tech as civil construction. If
one insisted on a cement story it would be *both* (metal core + pad), never
cement-only — but metal-only is the faithful call. Confidence: medium-high.

**RadiationShielding "Reinforced DU Wall" → METAL (keep Titanium+Lead, NO cement).**
Its identity is **depleted-uranium dense-metal radiation shielding**; the Lead in its
cost is the tell. The author expresses radiation shielding exclusively as Lead (a
metal) — never concrete — and cements exactly one wall-like def (VFES_ConcealedBarrier,
a plain steel barrier with no shielding identity). Cementing a "DU wall" erases what
it is. This is the closest of the three to a cement reading (it IS a bulk structural
wall), so I hold it at medium-high, not high.

**DU_Blastdoor → METAL (keep Titanium, NO cement). Confidence: high.** Blast doors
are dense-metal (steel/DU) slabs, not concrete slabs; the author cements **zero**
doors anywhere (EMM-Masonry's only ReBuild-Doors patch reworks glass, not a single
door), and the "DU"/radiation-shielding cue again points to metal. Clearest of the
three — reject cement outright.

Net: all three ambiguous resolve to **metal / do-not-cement**. The first-pass was
right to hesitate but the author's own roster (no door/wall/reactor/DU cement;
radiation = Lead) closes all three toward metal.

## MMP scan (128-building ledger, rows the first-pass does NOT touch)

The first-pass's assumption — leave the appliance/pipe/food/medical/computing/
refrigeration bucket metal-only with no cement — is **correct and appropriately
conservative.** I found no strong additional cement candidate. Checked and cleared:
- Heavy-but-non-structural: CoolingRadiator (350 steel), AirThermal/LargeAirThermal
  (600), JDS_RefrigeratedBoxTrucks (800), NuclearResearchBench (250) → all
  heat-exchange / storage / computing; the author never cements radiators, fridges,
  or research/consoles. Leave metal-only. Correct.
- "Vat/pod" lookalikes: VNPE_NutrientPasteVat, GR_NutrientVat → food-hygiene
  appliances (StainlessSteel), not the biotech *gestator/gene-pod* class the author
  cements. Leave. Correct.
- Deepchem *pipes/taps/valves/drain* → small StainlessSteel plumbing, not structural.
  Leave (only the pumpjack/refinery get cement). Correct.

One genuine **mis-metal** worth fixing (not a cement issue): **Radio_Industrial** is
`EM_Silicon 45%` tagged "high-strength frame." Silicon is the author's electronics
metal at the 12% tier (Joy_ModernComputer etc.); 45% is the frame tier. This row is
internally inconsistent — it should be Silicon ~12% (computing) like every other
computer/console. Likely an MMP copy-paste slip.

Cosmetic only: many StainlessSteel-45% rows (VCE_CheesePress, VCHE pipes,
VCE_VegMilkExtractor, GR_GeneticExtractionTable) carry a "high-strength frame"
reasoning string where "hygienic body" is meant — the 45% tier is shared between
Titanium(frame) and StainlessSteel(hygiene) and the note column drifted. Material is
fine; only the annotation is wrong.

## Cohesion

The list reads mostly like Argon's hand: conventional CE guns/artillery → cement
(his autocannon/minigun/siege bucket); magma/geothermal/steam/nuclear ARCs → cement
(his watermill/tidal/geothermal/nuclear bucket); deepchem + core drill → cement (his
pumpjack/helixien bucket); energy weapon + reactor → metal (his ship-turret/reactor
bucket). The three Rimatomics ambiguous defs correctly stay metal because his
radiation-shielding idiom is Lead, not concrete, and he cements no doors/walls/cores.

Two seams stand out as the least-faithful parts:

1. **The "both" set over-reaches, and on the wrong metal.** The author's ONLY real
   "both" precedent is the branded VFEFactory_* automation line (+ heavy standalone
   chambers he cemented *cement-only*). He pointedly left *plain* production benches
   (vanilla/VFE smelters, machining tables, fab benches — even the 300-steel large
   machining table) **metal-only, un-cemented**. Extending metal+cement to every
   smelter/machining/assembly bench is defensible-by-analogy but is the first-pass's
   main over-cementing risk. Only VFEFactory_DroneAutofactory is unimpeachable.
   RTC_EngineHanger and RT_AssemblyCrane are the weakest (bare structural frame/crane,
   no automation comp) and should probably be metal-only. And where metal is kept, the
   author would use **TemperedSteel** (his automation-machine metal), not the Titanium
   MMP inherited — so the "both" rows drift from his palette on *both* axes.

2. **Reason/label drift** (verdicts still fine): AB_BoneDistillery is cemented as a
   "deep-extraction drill" but is really a standalone bio-processor (its true analog
   is GenePod/gestator, which also lands on cement — right answer, wrong story).

Everything else is coherent and I'd ship it.

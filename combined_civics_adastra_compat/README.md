# Combined Civics - Ad Astra Compatibility

Compatibility patch for **Combined Civics** and the **4.5 Ad Astra** Irony Mod
Manager collection.

The active collection has two sources of conflict with Combined Civics:

- **Ad Astra** replaces `building_noble_estates` with an age-gated version.
- Irony's generated patch mod (`IronyModManager_4.5_Ad_Astra`) contains resolved
  versions of `building_noble_estates`, `building_institute`,
  `building_galactic_stock_exchange`, `holding_noble_vacation_homes` and the
  Archaeostudies Expertise traits.

Without this patch, those later definitions win and Combined Civics' changes
are lost. This patch merges the active collection's versions with the
Techno-Aristocratic Guilds checks.

## Load order

Irony's generated patch mod is loaded after the regular collection mods. If it
is enabled, simply adding this mod to the collection is not enough: the patch
mod's resolved definitions would still win.

Use one of these approaches:

- Regenerate the Irony patch mod after adding Combined Civics and this
  compatibility mod, and make sure the compatibility mod's versions win in the
  conflict solver.
- Or add the compatibility files to the generated patch mod's `common`
  directories with a `zzzzz_` prefix, so they load after the patch mod's `zzz_`
  files. This is what the current installation uses; regenerating the Irony
  patch mod will remove those copies.

The patch files themselves use a `zzzz_` prefix so they also load after Ad
Astra's `zzz_adastra_building_ages.txt` when file name order matters.

## Contents

- `common/buildings/zzzz_combined_adastra_buildings.txt` - merged Noble Estates,
  Research Institute, Galactic Stock Exchange and Noble Chateaus definitions.
- `common/traits/zzzz_combined_adastra_traits.txt` - merged Archaeostudies
  Expertise traits.

Ad Astra's early-age cleanup still removes Noble Estates before the medieval
age; the building can be constructed again once the Ad Astra age gate allows it.

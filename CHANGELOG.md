# Changelog

All notable changes to the mods in this repository. Entries are grouped by
date, newest first, and are derived from the commits on `main`.

## 2026-11-25

### Mosaic Pioneers
- Added the mod. It adds the player-only **Mosaic Pioneers** origin, which has
  the Great Mosaic's +1 civic slot and starts with Arc Furnace, Dyson Swarm,
  Terrestrial Sculpting, Ecological Adaptation, Climate Restoration and
  Orbital Habitats technologies.
- The origin uses the Great Mosaic icon and event picture, requires the Machine
  Age DLC, and is unavailable to nomadic empires.

## 2026-11-24

### Haruspex
- Fixed the **Haruspex Creed** civic being unavailable with the Absolute
  Spiritualist ethic added in 4.6. The civic's requirements now include
  `ethic_absolute_spiritualist`, so the job swaps also remain active when an
  empire upgrades from Fanatic to Absolute Spiritualist.

## 2026-11-23

### Fortress Designation for Ecumenopolis
- Updated for Stellaris 4.6.0 and bumped `supported_version` to `4.6.*`.
- Added weighting for 4.6 fortress zones and `@stickiness` while the
  designation is current, matching the 4.6 colony designation schema.

### Haruspex
- Updated for Stellaris 4.6.0 and bumped `supported_version` to `4.6.*`.
- Refreshed the Haruspex and Technophant job overrides against
  `common/pop_jobs/13_machine_age_jobs.txt`. No vanilla job changes were needed
  beyond the existing trait-gate removals.

### Megastructure System Limit Removal
- Updated for Stellaris 4.6.0 and bumped `supported_version` to `4.6.*`.
- Synced the full megastructure overrides with 4.6.0, restoring the
  `ideological_push_mult` station modifiers on the Science Nexus and
  Interstellar Assembly stages 1-4.

## 2026-11-18

### Combined Civics
- Added the mod. It adds the **Techno-Aristocratic Guilds** civic, combining
  Technocracy, Merchant Guilds and Aristocratic Elite, and the **Philosopher
  Admiralty** civic, combining Diplomatic Corps, Distinguished Admiralty and
  Philosopher King.
- Both civics are permanent and can only be chosen at empire creation.
- The combined civics and their source civics are mutually exclusive in both
  directions.
- Extended the Noble Estates, Noble Chateaus, Research Institute, Galactic
  Stock Exchange and Archaeostudies Expertise trait definitions, plus the
  Politician job-swap triggers, to recognize the combined
  Techno-Aristocratic Guilds civic.
- Added a Senior Science Director council position and a Lord High Admiral
  council position for the combined civics.

### Combined Civics - Ad Astra Compatibility
- Added a compatibility mod for the `4.5 Ad Astra` Irony Mod Manager
  collection.
- Merged Combined Civics' civic checks with Ad Astra's age-gated Noble Estates
  and with the Irony patch mod's resolved versions of Noble Estates, Research
  Institute, Galactic Stock Exchange, Noble Chateaus and Archaeostudies
  Expertise traits.
- Added `zzzzz_` copies of the merged definitions to the current
  `IronyModManager_4.5_Ad_Astra` patch mod so they load after its `zzz_` files.
  Regenerating the Irony patch removes these copies.
- No other conflicts were found with the active collection.

### Ad Astra + Planetary Diversity - More Arcologies Patch
- Added the patch. Both mods override `district_city`, so only one version
  applied in game.
- The merged definition keeps Ad Astra's age-based district upkeep and
  Planetary Diversity - More Arcologies' Garden, Fortress and Commercial
  Arcology Housing conversion targets.
- Ship the merged definition in `zzzz_adastra_pd_district_city.txt` so it loads
  after both mods' district files.

## 2026-11-16

### Haruspex
- Trimmed the **Haruspex Creed** civic tooltip so requirements, modifiers and
  council-position details are not repeated. It now lists only the Sanctum
  unlock and the job conversions.
- Added the building icon to the Sanctum unlock line.

## 2026-11-11

### Fortress Designation for Ecumenopolis
- Migrated the Ecumenopolis fortress designation to the Stellaris 4.5.4 colony
  designation schema. The deprecated `allow` and `ai_weight` blocks were
  replaced with `weight_modifier`, and `ai_building_set_affinity` was added so
  the AI favors fortress buildings under this designation.
- Bumped `supported_version` to `4.5.*`.
- Refreshed version references in the repository and mod READMEs.

### Haruspex
- Made the **Haruspex Creed** civic a permanent civic: it can only be selected
  at empire creation and cannot be removed afterwards.
- Replaced the extra Civic Slot with +1 Physics and Society Research per 100
  Haruspex, Technophant or Bureaucrat Jobs.
- Switched the civic icon to the vanilla Cybernetic Creed origin icon.
- Updated the civic tooltip and README to describe the permanent civic and
  research bonus.

## 2026-11-08

### Megastructure System Limit Removal
- Mega Shipyard construction stages now set `use_planet_resource = yes`, so the
  star's deposits are collected by the shipyard instead of being lost when the
  orbital station is dismantled.

### Haruspex
- Listed Haruspex in the repository contents.

## 2026-11-07

### Megastructure System Limit Removal
- Added the mod, removing the per-system "no existing megastructure"
  restriction for the Mega Shipyard, Sentry Array, Strategic Coordination
  Center, Science Nexus, and Interstellar Assembly.
- Renamed the mod to **Megastructure System Limit Removal**.
- Documented the repository contents and supported Stellaris versions in the
  README.

## 2026-11-04

### Haruspex
- Updated the Haruspex and Technophant job overrides for Stellaris 4.5.3.

## 2026-10-25

### Haruspex
- Added the Haruspex mod scaffold.
- Added the **Haruspex Creed** civic and its Bureaucrat-to-Haruspex and
  Politician-to-Technophant job swaps.
- Required the Spiritualist ethic and excluded the Cybernetic Creed origin.
- Added the **Sanctum of the Haruspex** civic building.
- Added the **Chief Haruspex** council position.

## 2026-07-15

### Fortress Designation for Ecumenopolis
- Added localisation support for nine languages.
- Updated the supported Stellaris version to 4.4.*.

## 2026-06-16

### Repository
- Added the Fortress Ecumenopolis designation mod.
- Added the initial repository README.

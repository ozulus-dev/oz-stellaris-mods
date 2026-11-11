# Changelog

All notable changes to the mods in this repository. Entries are grouped by
date, newest first, and are derived from the commits on `main`.

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
- Granted a Civic Slot through `country_government_civic_points_add`. Civic
  modifiers are ignored during empire creation, so the civic still costs a pick
  at creation; the extra slot applies after the game starts.
- Switched the civic icon to the vanilla Cybernetic Creed origin icon.
- Updated the civic tooltip and README to describe the permanent/free behaviour.

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

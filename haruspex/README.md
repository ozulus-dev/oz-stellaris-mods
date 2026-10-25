# Haruspex

A Stellaris mod. This is a scaffold: the structure, metadata and localisation
plumbing are in place, but there is no gameplay content yet.

## Layout

| Path | Purpose |
| --- | --- |
| `descriptor.mod` | Mod metadata: name, tags, supported game version |
| `thumbnail.png` | Placeholder Workshop/preview image, 512x512 |
| `common/` | Game data definitions (buildings, jobs, edicts, components, ...) |
| `events/` | Event and on_action scripts |
| `localisation/english/` | English strings, one `*_l_english.yml` per content area |
| `interface/` | UI files (`.gui`) |
| `gfx/interface/icons/` | Icons referenced by `interface/` and `common/` (`.dds`) |

Empty folders are kept in git with a `.gitkeep` file. Delete the `.gitkeep`
once a folder has real content.

## Conventions

- Prefix every game ID with `haruspex_` to avoid collisions with vanilla and
  other mods (for example `haruspex_building_oracle`).
- Localisation keys match the game ID without the prefix pattern being
  mandatory, but keeping IDs and keys aligned makes files easy to grep.
- Localisation `.yml` files must be saved as **UTF-8 with BOM**. Stellaris
  silently ignores files without the BOM.
- Bump `supported_version` in `descriptor.mod` when Paradox releases a new
  major patch, then retest.
- The `tags` block controls Workshop categories; adjust it once the mod's
  actual scope is clear.

## Testing locally

1. Copy or symlink this folder into
   `Documents/Paradox Interactive/Stellaris/mod/haruspex/`.
2. Create `Documents/Paradox Interactive/Stellaris/mod/haruspex.mod` containing:

   ```
   name="Haruspex"
   path="mod/haruspex"
   ```

3. Enable **Haruspex** in the launcher's Playset tab.
4. Check `Documents/Paradox Interactive/Stellaris/logs/error.log` after launch.

A symlink to this repository folder is usually easiest, since edits are then
picked up without copying. Windows requires Developer Mode or an elevated
shell to create symlinks (`New-Item -ItemType SymbolicLink`).

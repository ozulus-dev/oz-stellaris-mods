# Megastructure System Limit Removal

Removes the "no existing megastructure in this system" restriction for these
megastructures only, so they can be built in a system that already contains
another megastructure:

- Mega Shipyard
- Sentry Array
- Strategic Coordination Center
- Science Nexus
- Interstellar Assembly

All other placement rules (survey, star type, borders, one-per-empire limits,
Cosmogenesis world restriction, etc.) are unchanged.

## Implementation

The mod overrides the vanilla megastructure definitions and removes the
`has_no_non_gate_megastructure = yes` check from each site's `possible` block:

- `common/megastructures/02_spy_orb.txt` (Sentry Array)
- `common/megastructures/03_think_tank.txt` (Science Nexus)
- `common/megastructures/07_strategic_coordination_center.txt`
- `common/megastructures/09_interstellar_assembly.txt`
- `common/megastructures/11_mega_shipyard.txt`

These files are full copies of the Stellaris 4.5.4 versions. They will need to
be refreshed if a game update changes the vanilla definitions.

The Mega Shipyard stages also set `use_planet_resource = yes`. Vanilla
dismantles the star's orbital station when the shipyard is completed; with this
flag the shipyard collects the star's deposits itself, so those resources are
not lost.

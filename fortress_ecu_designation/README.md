# Fortress Designation for Ecumenopolis

Adds a **Fortress Ecumenopolis** colony designation for Ecumenopolis worlds,
built around defense and soldier training.

The designation:

- Is available on colonized Ecumenopolis worlds that are not the empire
  capital.
- Increases army build speed by 25%.
- Reduces orbital bombardment damage by 25%.
- Increases army defense damage by 25%.
- Increases Soldier job workforce by 25%.
- Adds 3 defense armies to the planet.

All other colony designations are unchanged, and Ecumenopolis worlds remain
eligible for their normal trade, industrial, foundry, factory and research
designations.

## Implementation

The mod adds a new colony type in
`common/colony_types/fortress_ecu_designation.txt`:

- `potential` restricts it to colonized Ecumenopolis worlds that are not the
  capital.
- `weight_modifier` gives it weight when the colony has a Stronghold or
  Fortress, so it is selected automatically once defenses are built.
- `ai_building_set_affinity` makes the AI favor fortress buildings while the
  designation is active.
- `planet_modifier` applies the army and defense bonuses listed above.

The mod does not override any vanilla definitions, so it should not conflict
with other mods unless they add their own Ecumenopolis fortress designation. It
reuses the vanilla `GFX_colony_type_fortress` icon.

Localisation is included for English, Brazilian Portuguese, French, German,
Japanese, Korean, Polish, Russian, Simplified Chinese and Spanish.

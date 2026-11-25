# Mosaic Pioneers

Adds the **Mosaic Pioneers** origin for Stellaris 4.6. It is a player-only
variant of the Great Mosaic that starts with the technologies needed to build
new homes and new power sources.

The origin:

- Grants the Great Mosaic's **+1 civic slot** modifier
  (`country_government_civic_points_add = 1`).
- Starts with the **Arc Furnace**, **Dyson Swarm**, **Terrestrial Sculpting**,
  **Ecological Adaptation**, **Climate Restoration** and **Orbital Habitats**
  technologies already researched.
- Uses the Great Mosaic origin icon and event picture.
- Cannot be selected by the AI: it sets
  `ai_playable = { always = no }`, `ai_weight = { weight = 0 }` and
  `random_weight = { base = 0 }`, so AI empires never generate with it.
- Requires the **Machine Age** DLC, because the Arc Furnace and Dyson Swarm
  technologies are part of that DLC.
- Is unavailable to nomadic empires, whose technology tree does not support
  terraforming or habitats.

## Implementation

The mod does not override any vanilla file. It adds:

- `common/governments/civics/mosaic_pioneers_origins.txt` - the origin
  definition.
- `events/mosaic_pioneers_events.txt` - a hidden startup event that grants the
  six technologies.
- `common/on_actions/mosaic_pioneers_on_actions.txt` - adds the event to
  `on_game_start_country`.
- `localisation/english/mosaic_pioneers_l_english.yml` - origin name,
  description and effect tooltip.

The technologies are granted with `give_technology` at game start, the same
mechanism vanilla uses for origin-specific technologies, rather than being
added as research options. The startup event is gated on
`has_origin = origin_mosaic_pioneers`, so it does nothing for any other empire.

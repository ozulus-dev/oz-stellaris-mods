# Ad Astra + Planetary Diversity - More Arcologies Patch

Compatibility patch for **Ad Astra** and **Planetary Diversity - More
Arcologies**. Both mods override the vanilla `district_city` district, so
without this patch only one mod's changes apply.

The patch merges both versions of `district_city`, keeping:

- Ad Astra's age-based upkeep: city districts cost energy once the empire pays
  energy upkeep, and minerals plus food before that (with the existing food
  upkeep on Wooden planets).
- Planetary Diversity - More Arcologies' extra conversion targets, so a city
  district can be upgraded into a Garden, Fortress or Commercial Arcology
  Housing district.

Everything else in `district_city` - housing, build time, zone slots,
availability triggers, the Arcology Project lockout and the AI weighting - is
unchanged from vanilla.

## Load order

The patch must load **after** both mods:

1. Planetary Diversity
2. Planetary Diversity - More Arcologies
3. Ad Astra
4. Ad Astra + Planetary Diversity - More Arcologies Patch

The descriptor lists the other mods as dependencies, so the Paradox launcher
sorts it last automatically. In Irony Mod Manager, place the patch at the bottom
of the playset and re-run the merge.

## Implementation

The mod adds a single file,
`common/districts/zzzz_adastra_pd_district_city.txt`, which contains the merged
`district_city` definition. The `zzzz_` prefix makes it load after both
`00_urban_districts.txt` (vanilla and PD - More Arcologies) and
`zzz_adastra_district_ages.txt` (Ad Astra), so the merged definition wins
regardless of the relative order of the two mods.

The file is a copy of Ad Astra's `district_city` block with the three PD -
More Arcologies arcology housing districts added to `convert_to`:

- `district_pd_garden_arcology_housing`
- `district_pd_fortress_arcology_housing`
- `district_pd_commercial_arcology_housing`

It will need to be regenerated if either mod changes `district_city`.

## Not covered

Ad Astra also overrides `district_generator`, `district_mining` and
`district_farming`, and PD - More Arcologies overrides the other urban,
arcology and ring world districts. Those definitions do not overlap, so they are
left to the original mods.

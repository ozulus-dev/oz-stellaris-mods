# Combined Civics

Adds two civics that fold several vanilla civics into one:

- **Techno-Aristocratic Guilds** combines **Technocracy**, **Merchant Guilds**
  and **Aristocratic Elite**.
- **Philosopher Admiralty** combines **Diplomatic Corps**,
  **Distinguished Admiralty** and **Philosopher King**.

Both civics are permanent: they can only be selected during empire creation and
cannot be added or removed afterwards.

## Techno-Aristocratic Guilds

Follows the requirements of **Aristocratic Elite**: it requires an Oligarchic or
Imperial authority, cannot be Egalitarian, cannot be Gestalt or Corporate, and
cannot be combined with the Unplugged origin. It also cannot be taken alongside
Technocracy, Merchant Guilds or Aristocratic Elite, and those civics cannot be
taken alongside it.

It keeps:

- The Technocracy Research Alternative bonus and Politician-to-Science Director
  conversion.
- The Merchant Guilds Politician-to-Merchant conversion.
- The Aristocratic Elite Politician-to-Noble conversion, Noble Estates
  building, Noble Chateaus holding, ruler workforce bonus and leader
  upkeep increase.
- The Technocracy bonus to Expertise traits.
- The Technocracy Research Institute and Merchant Guilds Galactic Stock
  Exchange extra Politician Jobs.
- The Technocracy council position, as **Senior Science Director**.

It deliberately omits:

- Scientists starting with a random Expertise trait.
- The extra starting Scientist governor on the homeworld.
- The Technocracy Scientist and Official capacity changes.
- The Merchant Guilds and Aristocratic Elite council positions.
- The Aristocratic Elite leader chance for an extra positive and negative
  trait.

## Philosopher Admiralty

Follows the requirements of **Distinguished Admiralty**: it requires the
Militarist or Fanatic Militarist ethic, cannot be Gestalt or Corporate, and
cannot be taken alongside Diplomatic Corps, Distinguished Admiralty or
Philosopher King. It does not restrict authority. Those three civics also
cannot be taken alongside it.

It keeps:

- The Diplomatic Corps Envoy, Diplomatic Weight, Trust Cap and Improve
  Relations bonuses.
- The Distinguished Admiralty ship fire rate, Commander upkeep, Command Limit
  and initial Commander skill bonuses.
- The Philosopher King ruler skill bonus.
- The Distinguished Admiralty council position, **Lord High Admiral**.

It deliberately omits:

- The Diplomatic Corps council position.
- The Philosopher King council position.

## Implementation

The mod adds or overrides these definitions:

- `common/governments/civics/combined_civics.txt` (the two civics)
- `common/governments/civics/combined_civics_exclusions.txt` (the six vanilla
  source civics, updated to block the corresponding combined civic)
- `common/governments/councilors/combined_councilors.txt` (the two council
  positions)
- `common/scripted_triggers/combined_job_triggers.txt` (the Politician job
  swap triggers, extended with the new civic)
- `common/traits/combined_traits.txt` (the Archaeostudies Expertise traits,
  extended with the new civic)
- `common/buildings/combined_buildings.txt` (Research Institute, Galactic
  Stock Exchange, Noble Estates and Noble Chateaus, extended with the new
  civic)
- `common/starbase_buildings/combined_starbase_buildings.txt` (Orbital Ring and
  Arkship Noble Estates, extended with the new civic)
- `common/inline_scripts/game_start/civic_aristocratic_elite.txt` (starts with
  Noble Estates for the new civic)
- `common/inline_scripts/traits/technocracy_expertise_effects.txt` (Expertise
  trait bonus applies to the new civic)

Because the civics, buildings, traits and scripted triggers are full
replacements, any other mod that edits the same definitions will conflict, and
load order decides the winner. The overrides are copied from Stellaris 4.5.4.

The combined civics use the vanilla Technocracy and Distinguished Admiralty
civic icons. The council positions use the same tech and admiralty modifiers as
their vanilla counterparts.

The mod merges the core mechanical effects only. Vanilla event options,
government-form names, AI personality weights and other purely flavour hooks
that check for the original civics are not extended to the new civics.

## Compatibility

Ad Astra also replaces `building_noble_estates` with its own age-gated version,
and Irony's generated patch mod may contain resolved versions of several of the
same definitions. Use the separate **Combined Civics - Ad Astra Compatibility**
mod, placed after Combined Civics, Ad Astra and the Irony patch mod. It merges
those versions with the Techno-Aristocratic Guilds checks.

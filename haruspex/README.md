# Haruspex

Adds the Cybernetic Creed's two special jobs - **Haruspex** and **Technophant** -
to any Spiritualist Democratic, Oligarchic, Dictatorial or Imperial empire
through a new civic: the **Haruspex Creed**. The civic cannot be combined with
the Cybernetic Creed origin, which already provides the jobs.

The mod:

- Adds the `civic_haruspex_creed` civic. It requires the Spiritualist or
  Fanatic Spiritualist ethic, one of the four standard (non-corporate,
  non-gestalt) authorities, and an origin other than Cybernetic Creed.
- Can only be selected at empire creation and cannot be removed afterwards.
- Makes Haruspex, Technophant and Bureaucrat Jobs produce +0.01 Society,
  Engineering and Physics Research each, or +1 of each per 100 Jobs.
- Converts every Bureaucrat job into a Haruspex job and every Politician job
  into a Technophant job, empire-wide.
- Lifts the vanilla restriction that only Cybernetic pops can work these jobs,
  including the Technophant gate added in 4.5.3. Availability is gated by the
  Spiritualist ethic plus having the Cybernetic Creed **origin** or the
  Haruspex Creed **civic**, not by a species trait.
- Applies the same Spiritualist check to both job swaps, so abandoning
  Spiritualism reverts the jobs as well as invalidating the civic.
- Keeps the Cybernetic Creed origin's job swaps available and only lifts its
  pop trait gate; the origin still requires Spiritualism.
- Unlocks the `building_haruspex_sanctum`, a unity building that adds +100
  Technophant and +200 Haruspex Jobs, +10% Spiritualist attraction, and +5%
  unity from jobs.
- Unlocks the `councilor_haruspex_creed` ("Chief Haruspex") council position
  for Officials, giving +2% Bureaucrat Job Output per skill level. Haruspex
  jobs use the bureaucrat economic category, so they benefit too.

All other Cybernetic Creed content, including its five origin-specific branch
buildings, remains origin-only and unchanged. The Sanctum of the Haruspex is the
civic's own centerpiece, not a port of them.

## Implementation

The mod **fully overrides** four vanilla definitions:

- `bureaucrat_is_haruspex` (scripted trigger)
- `politician_is_technophant` (scripted trigger)
- `haruspex` (pop job)
- `technophant` (pop job)

Any other mod that edits the same definitions will conflict, and load order
decides the winner. The job overrides are copied from Stellaris 4.5.4; after a
patch, compare them against `common/pop_jobs/13_machine_age_jobs.txt`.

The mod's files are:

- `common/governments/civics/haruspex_civics.txt` (the Haruspex Creed civic)
- `common/buildings/haruspex_buildings.txt` (the Sanctum of the Haruspex)
- `common/governments/councilors/haruspex_councilors.txt` (the Chief Haruspex
  council position)
- `common/scripted_triggers/haruspex_scripted_triggers.txt` (the vanilla
  job-swap triggers extended with the civic)
- `common/pop_jobs/haruspex_jobs.txt` (full overrides of the Haruspex and
  Technophant jobs, with the trait gates removed)
- `localisation/english/haruspex_l_english.yml` (civic text and updated job
  descriptions)

The civic reuses the vanilla Cybernetic Creed origin icon
(`gfx/interface/icons/origins/origins_cybernetic_creed.dds`).

The civic sets `modification = no`, making it a permanent civic: it can only be
chosen during empire creation and cannot be added or removed afterwards. Its
`planet_bureaucrats_*_research_produces_add = 0.01` modifiers apply to every Job
in the bureaucrat economic category, including Haruspex and Technophant.

The `politician_is_technophant` override also applies the Spiritualist check
that vanilla only applies to the Haruspex swap. A Cybernetic Creed empire that
abandons Spiritualism therefore loses both jobs; vanilla would have kept the
Technophant. This is deliberate, so both jobs follow the same rule.

The jobs keep their vanilla output. A job swap applies the base
Bureaucrat/Politician production plus the vanilla swap modifiers, so the
effective numbers are approximately:

- **Haruspex**: 2 Unity, 1 Engineering Research and extra Amenities; 2 Consumer
  Goods upkeep (compared with a Bureaucrat's 3 Unity).
- **Technophant**: 5 Unity, 2 Engineering Research and extra Amenities; 3
  Consumer Goods upkeep (a straight Engineering addition to the Politician).

The Haruspex trades 1 Unity for 1 Engineering; the Technophant is close to a
straight upgrade. That is the first pair of numbers to tune if the civic feels
too strong.

The civic also adds +0.01 Physics, Society and Engineering Research per
Haruspex, Technophant or Bureaucrat Job, or +1 of each per 100 Jobs.

The Sanctum of the Haruspex adds another +100 Technophant and +200 Haruspex
Jobs, +10% Spiritualist attraction, and +5% unity from jobs. It is limited to
one per planet and three per empire, costs a mid-tier building slot, and
requires Planetary Government, so it is a solid but not free addition.

The Chief Haruspex councilor adds +2% Bureaucrat Job Output per skill level.
At level 10 that is +20%, and because Haruspex jobs use the bureaucrat economic
category, it applies to them as well as to any remaining Bureaucrat jobs.

The mod uses vanilla job art and copies only the two affected job blocks, so
their `possible` gates can be changed; everything else stays in the base game.

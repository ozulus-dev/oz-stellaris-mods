# Haruspex

Adds the Cybernetic Creed's two special jobs - **Haruspex** and **Technophant** -
to any Spiritualist Democratic, Oligarchic, Dictatorial or Imperial empire
through a new civic: the **Haruspex Creed**. The civic cannot be combined with
the Cybernetic Creed origin, which already provides the jobs.

## What it does

- Adds the `civic_haruspex_creed` civic. It requires the Spiritualist or
  Fanatic Spiritualist ethic, one of the four standard (non-corporate,
  non-gestalt) authorities, and an origin other than Cybernetic Creed.
- Converts every Bureaucrat job into a Haruspex job and every Politician job
  into a Technophant job, empire-wide.
- Lifts the vanilla restriction that only Cybernetic pops can work these jobs.
  Availability is gated by the Spiritualist ethic plus having the Cybernetic
  Creed **origin** or the Haruspex Creed **civic**, not by a species trait.
- Applies the same Spiritualist check to both job swaps, so abandoning
  Spiritualism reverts the jobs as well as invalidating the civic.
- Keeps the Cybernetic Creed origin's job swaps available and only lifts its
  pop trait gate; the origin still requires Spiritualism.

No new building is added: the civic works purely by swapping the existing jobs.

## Files

| Path | Purpose |
| --- | --- |
| `common/governments/civics/haruspex_civics.txt` | The Haruspex Creed civic |
| `common/scripted_triggers/haruspex_scripted_triggers.txt` | Extends the vanilla job-swap triggers with the civic |
| `common/pop_jobs/haruspex_jobs.txt` | Full override of the Haruspex job, with the trait gate removed |
| `localisation/english/haruspex_l_english.yml` | Civic text and updated job descriptions |
| `gfx/interface/icons/governments/civics/civic_haruspex_creed.dds` | Civic icon (29x29 ARGB, matching vanilla) |

## Compatibility

This mod **fully overrides** three vanilla definitions:

- `bureaucrat_is_haruspex` (scripted trigger)
- `politician_is_technophant` (scripted trigger)
- `haruspex` (pop job)

Any other mod that edits the same definitions will conflict, and load order
decides the winner. The job override is copied from Stellaris 4.5.2; after a
major patch, compare it against `common/pop_jobs/13_machine_age_jobs.txt`.

The `politician_is_technophant` override also applies the Spiritualist check
that vanilla only applies to the Haruspex swap. This means a Cybernetic Creed
empire that abandons Spiritualism loses both jobs; vanilla would have kept the
Technophant. This is deliberate, so both jobs follow the same rule.

The mod uses vanilla job art and the vanilla Technophant definition. Only the
Haruspex job block is copied, so its `possible` gate can be changed; everything
else stays in the base game.

## Balance

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

## Testing locally

1. Copy or symlink this folder into
   `Documents/Paradox Interactive/Stellaris/mod/haruspex/`.
2. Create `Documents/Paradox Interactive/Stellaris/mod/haruspex.mod` containing:

   ```
   name="Haruspex"
   path="mod/haruspex"
   ```

3. Enable **Haruspex** in the launcher's Playset tab.
4. Start a Spiritualist empire that does not use the Cybernetic Creed origin,
   take the **Haruspex Creed** civic, and check that the capital's Politician
   job reads **Technophant** and its Bureaucrat jobs read **Haruspex**.
5. Check `Documents/Paradox Interactive/Stellaris/logs/error.log` for script
   errors after launch.

Localisation files must stay **UTF-8 with BOM**; Stellaris ignores them
otherwise.

## Publishing

Before uploading to the Workshop, set `remote_file_id` in `descriptor.mod` and
bump `version` for each release.

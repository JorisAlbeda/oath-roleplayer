# Oath Roleplayer - World Codex: Cascade Map

_A lookup table for what else a given change usually touches. Paths
from `Oath-Cowork-File-Map.md`; schemas from `Oath-Cowork-Spec.md`.
Read it whenever a segment is about to touch more than one document —
per `Oath-Cowork-Bot-Rules.md`, "Reference material."_

Unlike a multi-layer world build, Oath has no retroactive-edit workflow
requiring the human's approval before a cascade proceeds — a legal turn
just needs every document it touches actually updated, not left half
done. So this map isn't a gate to pass through; it's a checklist to
name and clear in the same pass a segment already runs in. State the
cascade plainly before finalizing (a sentence is enough — "this also
updates the Map and personifies a new Codex entry") the same way
`oath-play-turn` already states its Supply number: a stated cascade is
checkable, a silent one isn't.

## Cascade sizes

**Low** — one document, self-contained, no further checking needed.

**Moderate** — two or three documents, all already named below; touch
all of them in the same pass.

**High** — touches legality itself, not just documents. Re-check
anything already decided this segment before finalizing, since a High
cascade can retroactively make an earlier step illegal.

## Common triggers

**Denizen recruited or Mustered — Moderate**
Touches: Board state's Map (remove the Denizen from its site's list),
Player state (a new Adviser row: Name, Source card, Ability, Ability
cost, Status active), Codex (`characters/` entry: Name, Description,
Location, History, Voice). All three share one Name. See Bot-Rules,
"Codex — using it in play" and "Voice — staying in character."

**Adviser Status changes — lost or discarded — Low**
Touches: Player state's Adviser row only. The Codex entry is untouched
— its Description and History stay as they are; only what this
character can still *do* changed, not who they *are*.

**Edifice flips — Moderate**
Touches: Board state's Map (that site's Name if it changes, Ability,
and Relics, overwritten in place, same entry), and usually a Chronicle
beat. Touches the Codex `locations/` entry only if that entry's own
Description references the site's current state closely enough that
leaving it as-is would read as wrong.

**Relic peeked at or taken — Low, but shared-wide**
Touches: Board state's Map's Relics field for that site, updated once,
for every seat simultaneously — not a private note for whoever peeked.
If taken, remove it from the Map entirely.

**Banners change, or a role changes (Usurper) — High**
Touches: Player state's Banners field, plus a legality re-check on
anything already decided this segment (per Bot-Rules, "Bookkeeping
discipline" — scan for this before deciding anything else, not after).
Also worth flagging to the human that this seat's Strategy file may be
worth an `oath-inspect-board` re-run soon, since a Banner or role change
can undercut an existing strategy's assumptions.

**Bond shifts in Converse — Low**
Touches: Characters' Bonds field for the affected character(s) only.
Most conversations won't move it at all — see `oath-conclude-conversation`
step 4.

**A conversation surfaces something Codex-worthy — Low**
Touches: the relevant Codex entry's History (if it already exists), or
a new entry in the matching subfolder (if it doesn't). Most
conversations won't touch the Codex at all — see Bot-Rules, "Codex —
using it in play."

**A Live thread resolves or a new one emerges — Low, narrative-only**
Touches: Chronicle's own `## Live threads` header only — never Board
state, Player state, or legality. See Bot-Rules, "Live threads —
narrative-only tension tracking."

**Game ends — Special, once per game**
Touches: `Game/Story/Legacy/legacy-<colour>.md`, written by
`oath-leave-legacy` after reading Chronicle's final beats, this seat's
own Diary, the Codex, and the Endgame-Before/Endgame-After photographs.
Not part of the Play turn/End turn chain, and the only trigger here
that isn't checked for during ordinary play.

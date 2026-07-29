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
cost, Status active). If taken faceup, also touches Codex
(`characters/` entry: Name, Description, Location, History, Voice) in
the same pass — all three share one Name. If taken facedown, the Codex
entry waits — see "Adviser Revealed" below. See Bot-Rules,
"Codex — using it in play" and "Voice — staying in character."

**Adviser Revealed — Low**
Touches: Codex only — the `characters/` entry (Name, Description,
Location, History, Voice) that a facedown Adviser didn't get at
recruitment. Its Player-state row already exists and needs no change;
this just catches the Codex up to match a card that's now public. See
Bot-Rules, "Codex — using it in play," "A card taken facedown stays
unpersonified until Revealed."

**Adviser Status changes — lost or discarded — Low**
Touches: Player state's Adviser row only. The Codex entry is untouched
— its Description and History stay as they are; only what this
character can still *do* changed, not who they *are*.

**Vision revealed, or a held one discarded/replaced — Low**
Touches: Player state's Revealed Vision field only — set to the newly
revealed Vision's Name and Goal, discarding whatever it held before (a
seat can only hold one at a time, per the rules), or set back to "none"
if this seat is Defeated. Only Exiles can hold one faceup. Earns the
turn's Diary its own dedicated paragraph beyond the usual three, per
Bot-Rules "Diary — structure" — that's a content requirement on a
document already being written this segment, not a new document, so it
doesn't bump the size. Also conditionally worth a short note to
Personality description in Characters if it shifts this character's
stated Motivation, per Bot-Rules "Character creation — background
flavor and starting social circle" — same conditional-touch restraint
as Bonds, doesn't bump the size either.

**Edifice flips — Low**
Touches: Board state's Map only (that site's Name if it changes,
Ability, and Relics, overwritten in place, same entry) — no different
from any other Map upkeep edit. Only touches the Codex `locations/`
entry if that entry's own Description references the site's current
state closely enough that leaving it as-is would read as wrong; that
conditional touch doesn't bump the size, the same way the Chronicle
beat every segment gets regardless doesn't.

**Relic peeked at or taken — Low, but shared-wide**
Touches: Board state's Map's Relics field for that site, updated once,
for every seat simultaneously — not a private note for whoever peeked.
If taken, remove it from the Map entirely.

**Banners change, or a Role changes (Usurper flip, Citizenship offered
or accepted, a Citizen exiled back out) — High**
Touches: Player state's Banners field, its Role field, plus a legality
re-check on anything already decided this segment (per Bot-Rules,
"Bookkeeping discipline" — scan for this before deciding anything else,
not after). Also worth flagging to the human that this seat's Strategy
file may be worth an `oath-inspect-board` re-run soon, since a Banner or
Role change can undercut an existing strategy's assumptions. If the
Role change is genuine (not, say, a Citizenship offer merely made and
declined), it's also worth a short appended note to Personality
description in Characters reflecting the shift in Motivation, per
Bot-Rules, "Character creation — background flavor and starting social
circle" — conditional, the same restraint already used for Bonds, so it
doesn't bump this above High on its own.

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

---
name: oath-log-turn
description: Records the Human seat's own turn, reported directly by the human (Action 3 in Oath-Cowork-Spec.md). Use when the human describes what they did on their physical turn (e.g. "I moved to the Cauldrons and campaigned against Isolde").
---

# Oath — Log turn (Human seat)

Action 3 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
Guidance in `Oath-Cowork-Bot-Rules.md`, "Pre-flight check — required vs
recommended," and in `Oath-Cascade-Map.md` if this turn ends up
touching more than the documents named below. The Human seat has no bot
of its own to run oath-play-turn, so this is how their turn enters the
shared documents.

## The boundary

Read `Game/Mechanics/oath-board-state.md`,
`Game/Mechanics/oath-player-state.md`, and
`Game/Mechanics/oath-logic-log.md`. The human's own description is the
narrative source — there's no private Diary to check for the
Human seat. Steps below may also write to the Codex and
`Game/Story/oath-characters.md` when the reported turn actually touches
them (a faceup recruit, a Reveal, a Vision played faceup, a genuine Role
change).

## Steps

1. Take the human's own description of their turn as given.
2. Required-tier pre-flight check (Bot-Rules) against this seat's own
   Player-state row and whatever site the reported turn touched. If
   something Required is genuinely missing, say so plainly before
   recording anything; Recommended-tier gaps (no strategy file, a Codex
   entry with no Voice yet) just get noted, never block.
3. Update `Game/Mechanics/oath-player-state.md` with the mechanical
   results (Location, Region, Supply/Secrets/Favors gained or spent,
   Banners, Adviser rows). If the human recruited a new denizen, adviser,
   or commander (not a Vision — see steps 5-6 below) this turn, add its
   Adviser row here regardless of facing. If taken faceup, also
   personify it in the Codex now, the same way `oath-play-turn` does —
   Name/Description/Location/History/Voice to the Codex's `characters/`
   subfolder, matching Name — per `Oath-Cascade-Map.md`'s "Denizen
   recruited or Mustered" entry. If taken facedown, skip the Codex entry
   for now. Read the file fresh immediately before appending.
4. If the human's turn included Revealing a previously-facedown Adviser,
   personify it now in full (Description, Location, History, Voice), per
   `Oath-Cascade-Map.md`'s "Adviser Revealed" entry. Read the Codex
   fresh immediately before writing.
5. If the human's turn drew a Vision and kept it facedown as an adviser
   (rather than immediately playing it faceup, step 6, or discarding it),
   add a placeholder Adviser row now — Name "Vision (unrevealed)",
   Source card/Ability/Ability cost "unknown until Revealed", Status
   active — never its real identity, per Bot-Rules "Codex — using it in
   play," "A facedown Vision is a narrower case than a facedown
   denizen," and `Oath-Cascade-Map.md`'s "Vision drawn and kept facedown
   as an adviser" entry. It never gets a Codex entry, even once Revealed
   — it's not a person. Read the file fresh immediately before
   appending.
6. If the human's turn played a Vision faceup — whether drawn faceup
   this turn or Revealed from a facedown placeholder per step 5 — update
   this seat's own Player-state Revealed Vision field with its Name and
   Goal now, discarding whatever it held before, and remove the
   placeholder Adviser row from step 5 if there was one — per
   `Oath-Cascade-Map.md`'s "Vision revealed" entry. Read the file fresh
   immediately before appending.
7. Update `Game/Mechanics/oath-board-state.md` with any Map changes the
   reported turn made, per Bot-Rules "Map upkeep" — a denizen removed
   from a site's own Denizens list once Mustered or recruited, Ruled by
   or Number of warbands changing, Content or Relics changing, an
   edifice flipping. Most turns won't touch the Map at all. Read the
   file fresh immediately before appending.
8. Add an entry to `Game/Mechanics/oath-logic-log.md` describing the
   actions taken. Read the file fresh immediately before appending.
9. Add a narrated beat to `Game/Story/oath-chronicle.md`, grounded in
   the human's own description, same specificity standard as any other
   Chronicle entry — if the human's turn played a Vision faceup, this
   beat earns the fuller, dedicated-paragraph treatment per Bot-Rules,
   "Diary — structure," since the Human seat has no Diary of its own to
   carry it instead. Read the file fresh immediately before appending.
10. If this seat's own Role genuinely changed this turn (Usurper flip,
    Citizenship offered or accepted, a Citizen exiled back out), or the
    human's turn played a Vision faceup, append a short note to
    Personality description in `Game/Story/oath-characters.md` reflecting
    the shift in Motivation, per Bot-Rules, "Character creation —
    background flavor and starting social circle" — only when it
    actually shifted, not on every turn. Read the file fresh immediately
    before appending.

## Response

Confirm what was logged. Nothing else needs to print.

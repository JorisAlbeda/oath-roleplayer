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
Human seat.

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
   or commander this turn, personify it the same way `oath-play-turn`
   does — Name/Description/Location/History/Voice to the Codex's
   `characters/` subfolder, matching Name to a new Adviser row here —
   see `Oath-Cascade-Map.md`. Read the file fresh immediately before
   appending.
4. Update `Game/Mechanics/oath-board-state.md` with any Map changes the
   reported turn made, per Bot-Rules "Map upkeep" — a denizen removed
   from a site's own Denizens list once Mustered or recruited, Ruled by
   or Number of warbands changing, Content or Relics changing, an
   edifice flipping. Most turns won't touch the Map at all. Read the
   file fresh immediately before appending.
5. Add an entry to `Game/Mechanics/oath-logic-log.md` describing the
   actions taken. Read the file fresh immediately before appending.
6. Add a narrated beat to `Game/Story/oath-chronicle.md`, grounded in
   the human's own description, same specificity standard as any other
   Chronicle entry. Read the file fresh immediately before appending.

## Response

Confirm what was logged. Nothing else needs to print.

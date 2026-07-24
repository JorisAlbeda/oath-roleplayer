---
name: oath-log-turn
description: Records the Human seat's own turn, reported directly by the human (Action 3 in Oath-Cowork-Spec.md). Use when the human describes what they did on their physical turn (e.g. "I moved to the Cauldrons and campaigned against Isolde").
---

# Oath — Log turn (Human seat)

Action 3 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
The Human seat has no bot of its own to run oath-play-turn, so this is
how their turn enters the shared documents.

## The boundary

Read `Game/Mechanics/oath-board-state.md` and
`Game/Mechanics/oath-logic-log.md`. The human's own description is the
narrative source — there's no private Diary to check for the
Human seat.

## Steps

1. Take the human's own description of their turn as given.
2. Update `Game/Mechanics/oath-board-state.md` with the mechanical
   results. Read the file fresh immediately before appending.
3. Add an entry to `Game/Mechanics/oath-logic-log.md` describing the
   actions taken. Read the file fresh immediately before appending.
4. Add a narrated beat to `Game/Story/oath-chronicle.md`, grounded in
   the human's own description, same specificity standard as any other
   Chronicle entry. Read the file fresh immediately before appending.

## Response

Confirm what was logged. Nothing else needs to print.

---
name: oath-game-setup
description: One-time game initialization (Action 6 in Oath-Cowork-Spec.md). Use at the very start of a new game, before any seat's own oath-setup-character runs, once the Oath, player colours, roles, and human/AI split are known.
---

# Oath — Game Setup

Action 6 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
Guidance in `Oath-Cowork-Bot-Rules.md`, "Pre-flight check — required vs
recommended," and in `Oath-Cascade-Map.md` if any step below ends up
touching more than the documents it names. Runs once per game, in
whichever chat the human is using to bootstrap the project — not
seat-specific.

## Steps

1. Create the `Game/` subfolder if it doesn't already exist, along with
   its structure: `Game/Mechanics/`, `Game/Setup/`, `Game/Story/`,
   `Game/Story/Conversation logs/`, `Game/Story/Messengers/`,
   `Game/Story/Diaries/`, and `Game/Story/Legacy/`. This is purely
   organizational here — see `Oath-Cowork-File-Map.md`.
2. Take as given: the Oath sworn, each player's colour, Role, and
   whether they're Human- or AI-controlled.
3. Create `Game/Mechanics/oath-board-state.md`: Round 0, Visions Drawn
   0, World Deck Search cost: 2 Supply, the given Oath, Current Player
   Turn set to the Chancellor's colour, and the Map in full — read the
   `Board Photographs` folder for this; it's the only time the whole
   board is ever photographed, so get it right now. One entry per
   Region, one sub-entry per Site within it: Name, Ability, Ruled by
   (Empire / Bandits / an Exile's name — unclaimed sites are ruled by
   Bandits, never "none"), Number of warbands, Relic cost, Content (if
   any), Number of defence dice, Relics (Name and Description if
   already peeked at in the photograph, otherwise "unknown"), and that
   site's own Denizens (Name, Suit, Ability cost, Ability).
4. Create `Game/Mechanics/oath-player-state.md`: one Player row per
   colour with Role, Controlled-by, and Number of Supplies (7 for
   everyone) filled in, and Number of Secrets 0, Number of Favors 0,
   Banners none, and Revealed Vision none for everyone — explicit
   zeroes/none, not left blank, so the Required pre-flight check has an
   actual value to find. Name stays blank for AI seats until their own
   Setup decides it; fill it in now for the Human seat if known.
5. Create empty `Game/Story/oath-characters.md`,
   `Game/Mechanics/oath-logic-log.md`, and `Game/Story/oath-chronicle.md`
   — the Chronicle starts with an empty `## Live threads` header at the
   top (per Bot-Rules, "Live threads — narrative-only tension tracking"),
   nothing under it yet.
6. For each AI-controlled seat, create an empty
   `Game/Story/Diaries/oath-diary-<seat>.md`, and
   `Game/Story/Messengers/oath-messengers-<seat>.md`.
7. For each AI-controlled seat, write
   `Game/Setup/oath-world-briefing-<seat>.md` — a paragraph grounding
   that seat's own upcoming Setup decision: named starting-location
   options (cross-checked against the Map just created) and the seat's
   own three starting-adviser options, as shown in that seat's own
   photo. Keep each seat's briefing to what that seat can actually see;
   don't leak another seat's options into it.
8. Do not create World Briefing files for the Human seat. Don't create
   Strategy files for anyone here either — `oath-inspect-board` creates
   a seat's own `Game/Mechanics/strategy-<colour>.md` lazily on its
   first run.
9. Before finishing, run the Required tier of the pre-flight check
   (Bot-Rules) against what was just created: Oath, Current Player Turn,
   and every seat's Role/Controlled-by set in Player state; every Map
   entry has at least Ruled by and Number of warbands. If anything's
   missing, say so plainly rather than handing off an incomplete board.

## Response

Confirm the documents created and which seats are AI vs. Human. Tell
the human which seat should run oath-setup-character next.

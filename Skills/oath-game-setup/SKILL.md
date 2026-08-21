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
   organizational here — see `Oath-Cowork-File-Map.md`. Do not create a
   Codex folder anywhere as part of this step, or any other — the Codex
   lives outside this project entirely, at `Catalogue/codex/`, already
   populated by the human; if it isn't visible from this session, that's
   a folder-access question for the human, never something to create.
2. Take as given: the Oath sworn, each player's colour, Role, and
   whether they're Human- or AI-controlled.
3. Create `Game/Mechanics/oath-board-state.md`: Round 0, Visions Drawn
   0, World Deck Search cost: 2 Supply, the given Oath, Current Player
   Turn set to the Chancellor's colour, Favor Banks (3 favor in each of
   the six banks — Discord, Hearth, Beast, Nomad, Order, Arcane; 4 each
   instead with 5 or 6 players, per 2.1.3/setup step 6), and the Map in
   full — read the
   `Board Photographs` folder for this; it's the only time the whole
   board is ever photographed, so get it right now. One entry per
   Region, one sub-entry per Site within it: Name, Ability, Ruled by
   (Empire / Bandits / an Exile's name — unclaimed sites are ruled by
   Bandits, never "none"; a freshly-dealt Site is unclaimed by
   definition), Number of warbands (a Bandit-ruled Site carries 1
   warband by default unless the photo clearly shows otherwise), Relic
   cost, Content (if any), Number of defence dice, Relics (Name and
   Description if already peeked at in the photograph, otherwise
   "unknown"), and that site's own Denizens (Name, Suit, Ability cost,
   Ability). Board state records only these current values — no
   rationale or history for how a value got there; that belongs in the
   Logic log.

   Filling in a Site's Ability, Number of defence dice, Denizen
   capacity, or Relic cost needs two different sources, not one: read
   `oath_rules.txt` section 2.8 for which of the card's four corners
   each field comes from, then read `Oath_Reference.pdf` page 2 (the
   actual Site Reference aid sheet) for what that corner's icon means —
   2.8 says where to look, the aid sheet says what's there. A Site's own
   Power (bottom-left corner) is never printed as card text at all, so
   the aid sheet lookup for it isn't optional; "not legible in the
   photo" is never the right conclusion for a Site's Power. Note that
   `Oath_Reference.pdf` is image-only — open and read it as an image,
   not a text search.

   A card with no ordinary suit crest, showing crossed-out restriction
   icons instead (a Ruin), is still a real Denizen belonging to whatever
   Site it sits at — record it in that Site's own Denizens list, not as
   a Vision or a stray reference card.

   Count each Region's own undiscovered Sites too, not just the faceup
   one(s): a facedown Site shows in the photograph as a plain green card
   with a white border and a blue compass. Add one `**Unknown site**`
   entry per such card — don't assume the one identified Site is the
   Region's only one.

   Each Region's own header shows a flat Search Discard Pile cost (2
   Supply, per rule 5.1.1) — this is distinct from Board state's own
   top-level World Deck Search cost, which instead scales with Visions
   Drawn (2.1.6). Don't conflate the two. Every Region's discard pile
   starts empty at Setup — record `Discard Pile: 0 cards` alongside
   each Region's Search Discard Pile cost.

4. Create `Game/Mechanics/oath-player-state.md`: one Player row per
   colour with Role, Controlled-by, and Number of Supplies (7 for
   everyone) filled in, and Number of Secrets 1, Number of Favors 2 for the Chancellor, 1 for everyone else,
   Banners as per the setup conditions, The Grand Scepter for the Chancellor and Revealed Vision none for all Exiles.
   zeroes/none, not left blank, so the Required pre-flight check has an
   actual value to find. Name stays blank for AI seats until their own
   Setup decides it; fill it in now for the Human seat if known.

   Also fill in Warbands in reserve, using the fixed total warband pool
   each Role starts with (24 for the Chancellor, shared with every
   Citizen; 14 for each Exile) minus whatever the setup photographs
   show already placed on that seat's own board and at sites they rule.
   For the Chancellor, count every Empire-ruled site's warbands
   (including any placed under a Citizen's local command) plus the
   Chancellor's own board — that combined total is what the whole
   Empire's reserve is measured against, so only the Chancellor's row
   carries a number. Give each Citizen row a one-line note instead
   ("shares the Chancellor's reserve — see Bot-Rules, 'Warband reserve
   and the Supply refresh table'"), not a number of their own.
5. Create empty `Game/Story/oath-characters.md`,
   `Game/Mechanics/oath-logic-log.md`, and `Game/Story/oath-chronicle.md`
   — the Chronicle starts with an empty `## Live threads` header at the
   top (per Bot-Rules, "Live threads — narrative-only tension tracking"),
   nothing under it yet.
6. For each seat, create an empty
   `Game/Story/Messengers/oath-messengers-<seat>.md`. For each
   AI-controlled seat only, also create an empty
   `Game/Story/Diaries/oath-diary-<seat>.md` — the Human seat gets a
   Messengers file (their character can still receive messages) but no
   Diary, since there's no bot of its own to write one.
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
   entry has at least Ruled by and Number of warbands; all six Favor
   Banks have exact counts; every Region has a Discard Pile count; every
   seat's Warbands in reserve is set (a number for an Exile or the
   Chancellor, the shared-reserve note for a Citizen). If anything's
   missing, say so plainly rather than handing off an incomplete board.

## Response

Confirm the documents created and which seats are AI vs. Human. Tell
the human which seat should run oath-setup-character next.

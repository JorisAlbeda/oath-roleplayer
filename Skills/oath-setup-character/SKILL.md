---
name: oath-setup-character
description: Creates this seat's own character in the same pass as their starting board placement (Action 2 in Oath-Cowork-Spec.md). Use once per AI-controlled seat, after oath-game-setup has run, when this seat is ready to join the game.
---

# Oath — Setup (one bot, one pass)

Action 2 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
AI-controlled seats only — the Human seat reports their own starting
Location via `oath-log-turn` like any other turn, since their
Supply/Secrets/Favors/Banners are already set by Game Setup.

## The boundary

Read this seat's own `Game/Setup/oath-world-briefing-<seat>.md`,
`Game/Story/Legacy/legacy-<colour>.md` if it exists, the Codex,
`Game/Story/Codex/timeline.md`, `Game/Mechanics/oath-board-state.md`,
and board/mat photographs including this seat's own starting-adviser
photo. Never read another seat's World Briefing, Legacy, or private
documents.

## Steps

1. Check your own World Briefing and the board/mat photographs.
2. Check for `Game/Story/Legacy/legacy-<colour>.md`. It won't exist for
   a colour's first-ever game — that's fine, skip straight to step 3. If
   it does exist, it holds only the most recent character who held this
   colour, headed `## <Character Name>` — read it, and let it genuinely
   shape this new character rather than treating it as flavor text to
   nod at. The Motivation, Flaw, or Bond below should
   visibly grow out of it where it makes sense (an heirloom carried
   forward, a debt inherited, a reputation to live down or live up
   to). Not required to force a connection if the legacy content
   doesn't suggest one, but check first. Also check for a portrait
   image in the same `Game/Story/Legacy/` folder, named after this
   colour, if one exists — a visual reference for whoever held this
   colour before. This is the only step where you'll actually see it,
   so note 2-3 concrete details now: an object, a posture, a piece of
   clothing — not mood or interpretation. Anything not written down
   here won't survive past this step.
3. Check the Codex for this seat's starting Location and starting
   adviser, if either already has an entry — most likely from the
   previous game. Per Bot-Rules, "Codex — using it in play," let
   established detail shape this character's Physical description,
   Personality description, or Bond the same way Legacy does above.
   Most starting points won't have one; that's fine.
4. Check `Game/Story/Codex/timeline.md`'s latest entries — human-
   maintained and read-only, never written to by this or any skill. Let
   the world's current era (what year of the Old Oak this is, what its
   most recent entry says just happened) ground this character's
   Motivation, Flaw, or Bond the same way Legacy and the Codex do above.
5. Decide, in the same pass: Location, Region, Name, Pronouns,
   Motivation, Flaw, a Bond with a previous character if one plausibly
   exists, and which starting adviser you're taking.
6. Personify the starting adviser immediately — add it to the Codex's
   `characters/` subfolder (Name, Description, Location, History),
   following the structure of the existing character files.
7. Add a full entry to `Game/Story/oath-characters.md`: Name, Pronouns,
   Role, Colour, Location, Physical description, Personality
   description, Bonds. Read the file fresh immediately before
   appending, per the append-only convention.
8. Update `Game/Mechanics/oath-board-state.md` with this seat's
   Location, Region, and Name. Read the file fresh immediately before
   appending, per the append-only convention.

## Response

Print the character created (Name, Pronouns, Location, Motivation, Flaw,
starting adviser and their description) so the human can relay it to
the physical board.

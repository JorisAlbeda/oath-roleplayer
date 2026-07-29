---
name: oath-setup-character
description: Creates this seat's own character in the same pass as their starting board placement (Action 2 in Oath-Cowork-Spec.md). Use once per AI-controlled seat, after oath-game-setup has run, when this seat is ready to join the game.
---

# Oath — Setup (one bot, one pass)

Action 2 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
Guidance in `Oath-Cowork-Bot-Rules.md`, "Character creation — background
flavor and starting social circle," for steps 5-7 below, "Voice —
staying in character," for step 8, and in `Oath-Cascade-Map.md` for the
fuller personification cascade. AI-controlled seats only — the Human
seat reports their own starting Location via `oath-log-turn` like any
other turn, since their Supply/Secrets/Favors/Banners are already set by
Game Setup.

## The boundary

Read this seat's own `Game/Setup/oath-world-briefing-<seat>.md`,
`Game/Story/Legacy/legacy-<colour>.md` if it exists, the Codex,
`Game/Story/Codex/timeline.md`, `Game/Mechanics/oath-board-state.md`,
`Game/Mechanics/oath-player-state.md`, and this seat's own
starting-adviser photo. Board state's Map already holds the whole
board from Game Setup's own photographs — no need to re-photograph it
here. Never read another seat's World Briefing, Legacy, or private
documents.

## Steps

1. Check your own World Briefing, the Map in Board state, and this
   seat's own starting-adviser photo.
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
5. Background Flavor, per Bot-Rules "Character creation — background
   flavor and starting social circle": sketch 2-3 short, concrete,
   sensory background options — two or three sentences each, implying a
   particular life rather than stating a trait — grounded in whatever
   Legacy, Codex, and Timeline material steps 2-4 surfaced. Choose one,
   or blend two, as this character's actual background.
6. Decide, in the same pass: Location, Region, Name, Pronouns,
   Motivation, Flaw, a Bond with a previous character if one plausibly
   exists, and which starting adviser you're taking — with Motivation,
   Flaw, and Bond visibly derived from the background just chosen, not
   picked independently of it. Motivation must also answer this seat's
   own Role, already set in Player state by Game Setup (Chancellor,
   Exile, or a Citizen carried over from a previous game) — why this
   character wants that Role's own stake in the Empire's fate, per
   Bot-Rules, "Character creation — background flavor and starting
   social circle."
7. Starting Social Circle, per the same Bot-Rules section: independent
   of whether the Bond above exists, establish 1-2 minor Acquaintances
   tied to this character's Location or the background just chosen — a
   name, a one-line relationship, and what they might know or want.
8. Personify the starting adviser immediately — starting advisers are
   taken faceup, so this happens now, split per Bot-Rules "Codex — using
   it in play": Name, Description, Location, History, and Voice (per
   "Voice — staying in character") to the Codex's `characters/`
   subfolder, following the structure of the existing character files.
9. Add a full entry to `Game/Story/oath-characters.md`: Name, Pronouns,
   Role, Colour, Location, Physical description, Personality
   description, Bonds, and any Acquaintances from step 7. Read the file
   fresh immediately before appending, per the append-only convention.
10. Update `Game/Mechanics/oath-player-state.md` with this seat's
    Location, Region, and Name, and a new Adviser row for the starting
    adviser — the same Name as step 8, plus Source card, Ability,
    Ability cost, and Status active. If this starting adviser was listed
    under a site's own Denizens in Board state's Map, remove it from
    there too — see `Oath-Cascade-Map.md`. Read each file fresh
    immediately before appending, per the append-only convention.
11. Before printing, run the Required tier of Bot-Rules' pre-flight
    check against this seat's own new row: Location, Region, Name set,
    and the new Adviser row has a Status.

## Response

Print the character created (Name, Pronouns, Location, the background
chosen in step 5, Motivation, Flaw, any Acquaintances, and the starting
adviser and their description) so the human can relay it to the
physical board.

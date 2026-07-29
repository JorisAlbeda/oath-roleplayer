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
`Game/Story/Legacy/legacy-<colour>.md` if it exists, the Codex and
`timeline.md` — both kept in the connected `codex` folder, outside this
project's own `Game/` tree, in its own git repository shared across
playtests, not copied in here — `Game/Mechanics/oath-board-state.md`,
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
4. Check the connected codex folder's `timeline.md` latest entries —
   human-maintained and read-only, never written to by this or any
   skill. Let
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
   Give it an actual life before this pass — a trade, a family, a debt, a
   loss, a reason it knows what it knows — the same depth as the
   Background Flavor in step 5, not a stub pointing back at this seat's
   own Setup.
9. Personify this seat's own new character in the Codex too, same
   `characters/` subfolder as step 8 but the player-character structure
   already used there for previous Truthwatchers, Exiles, and Citizens
   (Marren Wick, Iona Ashe, Rowan Voss, Sorrel Wick): Description,
   History, Location, and Status (`Active`) — no Voice field, that's
   adviser-only. Draw the Description and History straight from the
   background, Motivation, Flaw, and Bond already decided in steps 5-6;
   don't invent new detail here, just carry it over into Codex prose.
10. Personify this seat's own starting warbands too, per Bot-Rules
    "Warbands — personifying a seat's own forces" — not conditional the
    way an enemy's garrison is, do this every time. Whatever this seat
    starts the game holding gets a name, a leader (a minor Codex
    `characters/` entry), and a character: its own home site's standing
    garrison (Board state Map's Number of warbands there) as a Garrison
    field on that site's own Codex `locations/` entry, and whatever sits
    on this seat's own board (Player state) as its own dedicated Codex
    `characters/` entry — the company described in that entry's own
    Description, its leader named as the entry's subject. Let the site
    or this character's own background suggest both, the same way step 8
    let the adviser card suggest a life.
11. Language and Voice check, before any Codex entry above is actually
    written: draft the Description and History for steps 8, 9, and 10,
    then check the draft against Bot-Rules "Roleplayer — Guidelines"
    (in-world, not in-game) and, for the adviser and the two forces, their
    own Voice or character from step 8/10 — flag and rewrite any
    mechanical vocabulary (a card's own printed name, "Round 0," "this
    seat's starting adviser," "facedown"/"faceup") before it reaches the
    Codex. Don't move on to step 12 below until this passes clean.
12. Add a full entry to `Game/Story/oath-characters.md`: Name, Pronouns,
    Role, Colour, Location, Physical description, Personality
    description, Bonds, and any Acquaintances from step 7. Read the file
    fresh immediately before appending, per the append-only convention.
13. Update `Game/Mechanics/oath-player-state.md` with this seat's
    Location, Region, Name, and Number of Warbands on its own board (per
    step 10), and a new Adviser row for the starting adviser — the same
    Name as step 8, plus Source card, Ability, Ability cost, and Status
    active. If this starting adviser was listed under a site's own
    Denizens in Board state's Map, remove it from there too — see
    `Oath-Cascade-Map.md`. Read each file fresh immediately before
    appending, per the append-only convention.
14. Before printing, run the Required tier of Bot-Rules' pre-flight
    check against this seat's own new row: Location, Region, Name set,
    and the new Adviser row has a Status.

## Response

Print the character created (Name, Pronouns, Location, the background
chosen in step 5, Motivation, Flaw, any Acquaintances, and the starting
adviser and their description) so the human can relay it to the
physical board.

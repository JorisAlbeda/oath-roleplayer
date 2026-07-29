# Oath Roleplayer - World Codex: Data & Actions Spec

_One bot, two responsibilities — every Action below is written for a single
integrated agent that reasons about mechanics and writes narrative in
the same turn._

## Documents

1. Board state (shared mechanical truth, global)
   - Round
   - Visions Drawn
   - Oath
   - Current Player Turn
   - World Deck Search cost
   - Map (one entry per Region, one sub-entry per Site within it):
     - Name
     - Ability
     - Ruled by (Empire / Bandits / an Exile's name — unclaimed sites
       are ruled by Bandits, never "none"; only one faction rules a
       site at a time)
     - Number of warbands
     - Relic cost (e.g. three favors placed, two secrets burned)
     - Content (if relevant — most sites won't have this)
     - Number of defence dice
     - Relics (Name and Description once anyone has peeked at it;
       otherwise "unknown" — this is shared knowledge for every seat
       the moment anyone peeks, not a private note for whoever peeked)
     - Denizens (one per denizen present at the site, until Mustered or
       otherwise taken by a seat):
       - Name
       - Suit
       - Ability cost
       - Ability
   - Filled in full from board photographs once, during Game Setup —
     the only time the whole board is ever photographed. Kept current
     afterward from the Logic log alone, whenever Play turn, Log turn,
     or End turn touches the Map (a denizen Mustered off a site, an
     edifice flipping, Ruled by/warbands/Content/Relics changing).

2. Player state (shared mechanical truth, per seat)
   - Players:
     - Name
     - Role
     - Colour
     - Controlled by (AI or Human)
     - Location
     - Region
     - Number of Supplies
     - Number of Secrets
     - Number of Favors
     - Banners
     - Revealed Vision (Name, Goal — "none" if not currently held; an
       Exile's own held Vision, discarded and replaced the moment a new
       one is revealed, or discarded outright if this seat is Defeated)
     - Advisers (one per personified adviser/denizen/commander this seat
       holds — mechanical half only; the narrative half is the matching
       Codex `characters/` entry):
       - Name (must match this adviser's Codex entry exactly)
       - Source card
       - Ability
       - Ability cost
       - Status (active / lost / discarded)

3. Characters (shared narrative truth)
   - Players:
     - Name
     - Pronouns
     - Role
     - Colour
     - Location
     - Physical description
     - Personality description
     - Bonds
     - Acquaintances (lighter than Bonds — name, one-line relationship,
       what they might know or want; established at character creation,
       per Bot-Rules, "Character creation — background flavor and
       starting social circle")

4. Logic log
   - Turns:
     Actions taken

5. Diary (One per character)
   - A short diary entry each turn
   - Private to this seat

6. Chronicle
   - Shared narrative: for the player
   - A `## Live threads` header at the top (2-3 in-world tensions,
     narrative-only, overwritten as they resolve or emerge) — the one
     part of this file that isn't append-only, per Bot-Rules, "Live
     threads — narrative-only tension tracking"

7. Messengers (One per character)
   - New messages

8. World Briefing (One per character)
   - Paragraph for this seat's bot to ground its own character creation
     and board placement in the same pass, including this seat's own
     named starting-location options and its three starting-adviser
     options as shown in its photo — one per character, not shared,
     because the adviser photo is unique to each seat

9. Converse dialogue (One per conversation, cross-seat only — e.g.
   Lyn-Dorcas-R2-1 for the first conversation between them in Round 2)
   - Lines of in-character dialogue between two characters

10. Legacy (One per AI-controlled colour, append-only across games — not
    written or read by any of the eight Actions below; it's the input and
    output of a ninth, cross-game step, oath-leave-legacy, that runs
    once a game ends and feeds the next game's own Setup for that colour)
    - One `## <Character Name>` entry per previous character who held
      this colour: an in-world fragment (family record, heirloom, debt,
      reputation, rumor) left for that colour's next character to build
      from

11. Strategy (One per AI-controlled colour, not append-only — overwritten
    each time)
    - Two board observations, one sentence each
    - A three-point strategy for winning the game, one sentence per point
    - Kept current by `oath-inspect-board`, an eighth, standalone step
      that isn't part of the Play turn/End turn chain

12. Codex (Shared; one file per entry, in a `buildings`/`characters`/
    `events`/`locations`/`relics` subfolder matching its category)
    - Title, Description, History, Location
    - `characters/` entries carry a fifth field, Voice (vocabulary
      level, one or two verbal habits, emotional default, speech
      rhythm) — written once at personification, per Bot-Rules,
      "Voice — staying in character"
    - `locations/` entries may optionally carry Regional voice notes (a
      proverb or two, a conversational habit) — added the first time a
      scene actually happens there, not upfront
    - Mostly inherited from the previous game; read and extended during
      this one per Bot-Rules, "Codex — using it in play"

13. Timeline (Shared; one running file, `Game/Story/Codex/timeline.md`;
    human-maintained across games, not written by any of the eight
    Actions below)
    - Dated entries recording the world's history by era, occasionally
      with editorial commentary
    - Read-only, by Action 2 (Setup), to ground a new character in the
      world's current era — the same role Legacy plays for that
      character's own colour

## Actions

1. Play turn (one bot, one pass)
   - Pre-flight check, per Bot-Rules, "Pre-flight check — required vs
     recommended" — required data missing means stop and name the gap;
     recommended data missing means proceed and name the assumption
   - Scan Player state for Banners and role changes before anything else
   - Check Board state, Player state, Logic log (entries since this
     seat's own last turn), Characters, the Codex (whatever's relevant
     to this segment — not a chronological log, so nothing to diff
     "since last turn"), own Diary, Messengers
   - Board state and Player state are kept current from the Logic log —
     no board photographs to check after Game Setup's own initial ones
   - Decide the one best course of action, spending most or all of this
     seat's Supply by default (max 2 remaining), chaining decisions until Rest (the turn
     is genuinely over) or pausing on a Campaign, Search, or Converse
     whose outcome isn't known yet — see Bot-Rules, "Legal turn
     endings," for how a paused turn resumes
   - If a new adviser/denizen/commander is drawn or recruited this turn,
     add its Adviser row in Player state now regardless of facing — Name,
     Source card, Ability, Ability cost, Status active. If taken faceup,
     also personify it in the Codex now (Name, Description, Location,
     History, Voice), same Name as the Adviser row; if taken facedown,
     the Codex entry waits until it's Revealed — see `Oath-Cascade-Map.md`
     for the fuller cascade either way. If this segment instead Reveals a
     previously-facedown Adviser, personify it in full now, the same
     depth as any faceup recruit — see `Oath-Cascade-Map.md`'s "Adviser
     Revealed" entry. If it came off a site's own Denizens list in Board
     state's Map, remove it from there either way — it's now this seat's
     Adviser, not the site's
   - If this segment plays a Vision faceup, update Player state's
     Revealed Vision field now (discarding any previous one it held, per
     the rules) — see `Oath-Cascade-Map.md`'s "Vision revealed" entry;
     this also earns the turn's Diary entry its own dedicated paragraph
     per Bot-Rules, "Diary — structure," handled in the same pass as End
     turn
   - Supply gate: state the exact Supply number left. More than 2? Add
     another action and recheck, unless none is affordable — then say so

2. Setup (one bot, one pass) — AI-controlled
   seats only; a Human seat's Supply/Secrets/Favors/Banners are already
   set by Game Setup, and they report their own starting Location via
   Log turn like any other turn
   - Check briefing (own World Briefing, written by Game Setup)
   - Check Board state's Map and this seat's own starting-adviser photo
   - Check the Codex for this seat's starting Location or adviser, if
     either already has an entry, and let it shape the character below
     the same way Legacy does
   - Background Flavor: sketch 2-3 short, concrete background options
     grounded in Legacy/Codex/Timeline, then choose or blend one — per
     Bot-Rules, "Character creation — background flavor and starting
     social circle"
   - Decide, in the same pass: Location, Region, Name, Pronouns,
     Motivation, Flaw, and Bond with a previous character (if one
     exists) — all derived from the background just chosen, not decided
     independently of it — and which starting adviser you're taking.
     Motivation must also answer this seat's own Role (Chancellor,
     Exile, or a Citizen carried over from a previous game) — why this
     character wants that Role's own stake in the Empire's fate, per
     Bot-Rules, "Character creation — background flavor and starting
     social circle"
   - Starting Social Circle: alongside the Bond, establish 1-2 minor
     Acquaintances tied to this character's Location or background
   - Personify the starting adviser immediately — starting advisers are
     taken faceup, so this happens immediately, same split as Action 1 —
     Codex's characters subfolder (including Voice) for the narrative
     half, a Player-state Adviser row for the mechanical half — it's
     already "drawn," same as any other
   - Update Player state (Location, Region, Name) and Characters (full
     entry: Name, Pronouns, Role, Colour, Location, Physical description,
     Personality description, Bonds, Acquaintances)

3. Log turn (Pass the human's own actions and
   description) — for the Human seat only, since it has no bot of its
   own to run Action 1
   - Required-tier pre-flight check (per Bot-Rules) against this seat's
     own row and whatever site was touched, before recording anything
   - Update Player state (Location, Supply/Secrets/Favors, Banners,
     Adviser rows, added regardless of facing; faceup recruits also get a
     Codex entry now, facedown ones wait until Revealed) and Board state
     (any Map changes the reported turn made) per what was reported, and
     Logic log. If the human's own turn Reveals a previously-facedown
     Adviser, personify it in full now — see `Oath-Cascade-Map.md`'s
     "Adviser Revealed" entry. If the human's turn plays a Vision faceup,
     update Player state's Revealed Vision field the same way — see
     `Oath-Cascade-Map.md`'s "Vision revealed" entry
   - Update Chronicle with a narrated beat from the human's own
     description — a Vision reveal earns the fuller, dedicated-paragraph
     treatment per Bot-Rules, "Diary — structure," since the Human seat
     has no Diary of its own to carry it
   - If this seat's own Role genuinely changed this turn, or a Vision was
     revealed, append a short note to Personality description in
     Characters reflecting the shift in Motivation, per Bot-Rules,
     "Character creation — background flavor and starting social circle"

4. Continue conversation (Pass Converse
   dialogue) — cross-seat
   - Check Converse dialogue and this character's Codex Voice (per
     Bot-Rules, "Voice — staying in character")
   - Add one reply line
   - Repeat for the other character until one concludes, or the human
     calls Conclude conversation directly

5. Conclude conversation (Pass Converse
   dialogue)
   - Add closing line, checked against Voice the same way
   - Summarize outcome in both characters' Diary
   - If witnessed, add a story beat to Chronicle
   - If the relationship shifted, update Bonds in Characters
   - Codex upkeep if the conversation changed or surfaced something
     worth remembering — see Bot-Rules, "Codex — using it in play"
   - Return to Play turn for whichever seat was mid-turn when this
     conversation started

6. Game Setup (Pass Oath, player colours,
   roles, and which are Human-controlled)
   - Create Board state: Round 0, Visions Drawn 0, World Deck Search
     cost, the given Oath, Current Player Turn set to the Chancellor's
     colour, and the Map in full (every Region, every Site's Name,
     Ability, Ruled by, Number of warbands, Relic cost, Content, Number
     of defence dice, Relics, and Denizens) read from the board
     photographs — the only time the whole board is ever photographed
   - Create Player state: one Player row per colour with Role,
     Controlled-by, and Number of Supplies (fixed at 7 for everyone)
     filled in — Name blank for AI seats until their own Setup decides
     it, filled in now for the Human seat
   - Create empty Characters, Logic log, and Chronicle
   - Do not create Strategy files for anyone — `oath-inspect-board`
     creates one lazily for a seat's own colour on its first run
   - Do not create Diary or Messengers files for the Human seat
   - Before finishing, run the Required tier of Bot-Rules' pre-flight
     check against what was just created
   - Runs once per game, before any seat's own Setup

7. End turn
   - Language check, then a voice check right after it (per Bot-Rules,
     "Voice — staying in character") — does this segment's narration
     match the character's stored Voice, not just avoid mechanical
     vocabulary? Don't move on until both pass clean
   - Write a diary entry about the turn (Chronicle-quality prose, per the
     specificity standard in Bot-Rules) and update Player state
     (including any Adviser's Status, if it changed this segment, and its
     Revealed Vision field if this segment played one faceup), Board
     state (any Map changes this segment made — a denizen removed from a
     site, an edifice flipping with its new Ability and Relics, Ruled
     by/warbands/Content/Relics changing), Logic log, own Diary, and
     Chronicle — if this segment played a Vision faceup, its Diary entry
     gets a dedicated paragraph beyond the usual three, per Bot-Rules,
     "Diary — structure"
   - If this seat's own Role genuinely changed this segment, or a Vision
     was revealed, append a short note to Personality description in
     Characters reflecting the shift in Motivation, the same restraint
     already used for Bonds — most segments won't touch it
   - Opportunistically check whether this segment resolves or introduces
     a Live thread (per Bot-Rules) — most segments won't touch it
   - In response, print the diary entry followed by Player
     Instructions for the physical board

8. Inspect board
   - Read Board state and Player state.
   - Check your strategy file (strategy-<colour>.md file in the Game/Mechanics folder) if you have one. Check the strategy's viability against the current situation.
   - Finally, make two observations about the board (one sentence each) and devise a (new) strategy you'll follow for winning the game. Let each strategy consist of three bullet points with one sentence each. Write the observations and the strategy to your strategy file (create it if it does not exist yet).
   - Separately, give the Chronicle's Live threads list a skim (per
     Bot-Rules) — does anything on it feel stale enough to retire? This
     is a distinct check from the strategy above and must not influence
     it either way.

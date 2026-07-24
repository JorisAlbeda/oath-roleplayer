# Oath Experiment 6 - World Codex: Data & Actions Spec

_One bot, two responsibilities — every Action below is written for a single
integrated agent that reasons about mechanics and writes narrative in
the same turn._

## Documents

1. Board state (shared mechanical truth)
   - Round
   - Visions Drawn
   - Oath
   - Current Player Turn
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
     - Advisers (one per personified adviser/denizen/commander this seat
       holds — mechanical half only; the narrative half is the matching
       Codex `characters/` entry):
       - Name (must match this adviser's Codex entry exactly)
       - Source card
       - Ability
       - Ability cost
       - Status (active / lost / discarded)

2. Characters (shared narrative truth)
   - Players:
     - Name
     - Pronouns
     - Role
     - Colour
     - Location
     - Physical description
     - Personality description
     - Bonds

3. Logic log
   - Turns:
     Actions taken

4. Diary (One per character)
   - A short diary entry each turn
   - Private to this seat

5. Chronicle
   - Shared narrative: for the player

6. Messengers (One per character)
   - New messages

7. World Briefing (One per character)
   - Paragraph for this seat's bot to ground its own character creation
     and board placement in the same pass, including this seat's own
     named starting-location options and its three starting-adviser
     options as shown in its photo — one per character, not shared,
     because the adviser photo is unique to each seat

8. Converse dialogue (One per conversation, cross-seat only — e.g.
   Lyn-Dorcas-R2-1 for the first conversation between them in Round 2)
   - Lines of in-character dialogue between two characters

9. Legacy (One per AI-controlled colour, append-only across games — not
   written or read by any of the eight Actions below; it's the input and
   output of a ninth, cross-game step, oath-leave-legacy, that runs
   once a game ends and feeds the next game's own Setup for that colour)
   - One `## <Character Name>` entry per previous character who held
     this colour: an in-world fragment (family record, heirloom, debt,
     reputation, rumor) left for that colour's next character to build
     from

10. Strategy (One per AI-controlled colour, not append-only — overwritten
    each time)
    - Two board observations, one sentence each
    - A three-point strategy for winning the game, one sentence per point
    - Kept current by `oath-inspect-board`, an eighth, standalone step
      that isn't part of the Play turn/End turn chain

11. Codex (Shared; one file per entry, in a `buildings`/`characters`/
    `events`/`locations`/`relics` subfolder matching its category)
    - Title, Description, History, Location
    - Mostly inherited from the previous game; read and extended during
      this one per Bot-Rules, "Codex — using it in play"

12. Timeline (Shared; one running file, `Game/Story/Codex/timeline.md`;
    human-maintained across games, not written by any of the eight
    Actions below)
    - Dated entries recording the world's history by era, occasionally
      with editorial commentary
    - Read-only, by Action 2 (Setup), to ground a new character in the
      world's current era — the same role Legacy plays for that
      character's own colour

## Actions

1. Play turn (one bot, one pass)
   - Scan Board state for Banners and role changes before anything else
   - Check Board state, Logic log (entries since this seat's own last
     turn), Characters, the Codex (whatever's relevant to this segment —
     not a chronological log, so nothing to diff "since last turn"), own
     Diary, Messengers
   - Check board photographs if updated
   - Decide the one best course of action, spending most or all of this
     seat's Supply by default (max 2 remaining), chaining decisions until Rest (the turn
     is genuinely over) or pausing on a Campaign, Search, or Converse
     whose outcome isn't known yet — see Bot-Rules, "Legal turn
     endings," for how a paused turn resumes
   - If a new adviser/denizen/commander is drawn or recruited this turn,
     personify it now: Name, Description, Location, History to the
     Codex's characters subfolder; Name (matching), Source card, Ability,
     Ability cost, Status active to a new Adviser row in Board state
   - Supply gate: state the exact Supply number left. More than 2? Add
     another action and recheck, unless none is affordable — then say so

2. Setup (one bot, one pass) — AI-controlled
   seats only; a Human seat's Supply/Secrets/Favors/Banners are already
   set by Game Setup, and they report their own starting Location via
   Log turn like any other turn
   - Check briefing (own World Briefing, written by Game Setup)
   - Check board/mat photographs and this seat's starting-adviser photo
   - Check the Codex for this seat's starting Location or adviser, if
     either already has an entry, and let it shape the character below
     the same way Legacy does
   - Decide, in the same pass: Location, Region, Name, Pronouns,
     Motivation, Flaw, Bond with a previous character (if one exists),
     starting adviser
   - Personify the starting adviser immediately, same split as Action 1 —
     Codex's characters subfolder for the narrative half, a Board-state
     Adviser row for the mechanical half — it's already "drawn," same as
     any other
   - Update Board state (Location, Region, Name) and Characters (full
     entry: Name, Pronouns, Role, Colour, Location, Physical description,
     Personality description, Bonds)

3. Log turn (Pass the human's own actions and
   description) — for the Human seat only, since it has no bot of its
   own to run Action 1
   - Update Board state and Logic log per what was reported
   - Update Chronicle with a narrated beat from the human's own
     description

4. Continue conversation (Pass Converse
   dialogue) — cross-seat, unchanged in kind from Experiment 3
   - Check Converse dialogue
   - Add one reply line
   - Repeat for the other character until one concludes, or the human
     calls Conclude conversation directly

5. Conclude conversation (Pass Converse
   dialogue)
   - Add closing line
   - Summarize outcome in both characters' Diary
   - If witnessed, add a story beat to Chronicle
   - If the relationship shifted, update Bonds in Characters
   - Codex upkeep if the conversation changed or surfaced something
     worth remembering — see Bot-Rules, "Codex — using it in play"
   - Return to Play turn for whichever seat was mid-turn when this
     conversation started

6. Game Setup (Pass Oath, player colours,
   roles, and which are Human-controlled)
   - Create Board state: Round 0, Visions Drawn 0, the given Oath,
     Current Player Turn set to the Chancellor's colour, one Player row
     per colour with Role, Controlled-by, and Number of Supplies (fixed
     at 7 for everyone) filled in — Name blank for AI seats until their
     own Setup decides it, filled in now for the Human seat
   - Create empty Characters, Logic log, and Chronicle
   - Do not create Strategy files for anyone — `oath-inspect-board`
     creates one lazily for a seat's own colour on its first run
   - Do not create Diary or Messengers files for the Human seat
   - Runs once per game, before any seat's own Setup

7. End turn
   - Write a diary entry about the turn (Chronicle-quality prose, per the specificity
     standard in Bot-Rules) and update Board state (including any
     Adviser's Status, if it changed this segment), Logic log, own
     Diary, and Chronicle
   - In response, print the diary entry followed by Player
     Instructions for the physical board

8. Inspect board
   - Read the files in the `Board photographs` folder, which should be updated (if not, say so and abort).
   - Correct the board state as needed.
   - Check your strategy file (strategy-<colour>.md file in the Game/Mechanics folder) if you have one. Check the strategy's viability against the current situation.
   - Finally, make two observations about the board (one sentence each) and devise a (new) strategy you'll follow for winning the game. Let each strategy consist of three bullet points with one sentence each. Write the observations and the strategy to your strategy file (create it if it does not exist yet).

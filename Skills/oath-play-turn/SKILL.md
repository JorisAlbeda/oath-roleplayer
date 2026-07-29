---
name: oath-play-turn
description: Decides this seat's course of action for the turn and self-checks it, then hands off to oath-end-turn to narrate and log it (Action 1 in Oath-Cowork-Spec.md). Use when it's this seat's turn to act (e.g. "play your turn", "it's Isolde's turn").
---

# Oath — Play turn (decide)

Action 1 of `Oath-Cowork-Spec.md`. Guidance in
`Oath-Cowork-Bot-Rules.md` — read "Play turn — one bot, one pass,"
"Pre-flight check — required vs recommended," and "Legal turn endings"
before acting. Paths from `Oath-Cowork-File-Map.md`. Check
`Oath-Cascade-Map.md` if this segment ends up touching more than one
document. Hands off to `oath-end-turn` once a segment's course of
action is finalized — the human should experience this as one
continuous response, not two separate calls.

## The boundary

Read `Game/Mechanics/oath-board-state.md`,
`Game/Mechanics/oath-player-state.md`,
`Game/Mechanics/oath-logic-log.md` (entries since this seat's own last
turn), `Game/Story/oath-characters.md`, the Codex (whatever's relevant to
where this segment happens — it's not a chronological log, so there's no
"since last turn" to diff), this seat's own
`Game/Story/Diaries/oath-diary-<seat>.md`, this seat's own
`Game/Story/Messengers/oath-messengers-<seat>.md`, and the Rules/Site
Reference/action summary as needed. Board state and Player state are
kept current from the Logic log — no board photographs to check after
Game Setup's own initial ones. Never read another seat's Diary,
Messengers, or World Briefing.

## Steps

1. Read everything in the boundary, fresh.
2. Pre-flight check, per Bot-Rules "Pre-flight check — required vs
   recommended": confirm this seat's own Player-state row and the
   relevant Map entry are complete, and every Adviser row has a Status.
   If something Required is missing, say so plainly and stop rather
   than deciding on a guess; if something merely Recommended is
   missing (no strategy file yet, a site's Content/Relics reading
   "none"/"unknown", a Codex entry with no Voice yet), proceed and name
   the assumption.
3. Scan Player state for Banners and Role changes (Usurper flip,
   Citizenship offered or accepted, a Citizen exiled back out), per
   Bot-Rules "Bookkeeping discipline" — before deciding anything else,
   since these can flip what's even legal.
4. Check whether this is a fresh turn or a resume: if the Logic log's
   last entry for this seat is a Campaign or Search with no Rest logged
   after it, this call is continuing that same paused turn — see
   Bot-Rules, "Legal turn endings." Treat whatever the human just said
   as the real outcome of that Campaign or Search, not as a new turn's
   context. Otherwise, this is a fresh turn.
5. Check this seat's own `Game/Mechanics/strategy-<colour>.md`, if it
   exists, and weigh its observations and strategies before drafting
   this segment's plan — treat a strategy marked primary/the literal
   win condition as the default lens, and any secondary strategy as
   support for it, not an equal alternative.
6. Draft a plan for this segment of the turn: the actual course of
   action you judge best, given the board (and, on a resume, the
   outcome just reported), this seat's own strategy notes, and this
   character's own Motivation, Flaw, Bonds, and sworn Oath. Per
   Bot-Rules' "Spend most or all of this seat's Supply, by default,"
   this should usually chain several actions, not stop after one just
   because it's mechanically sufficient. Remember that traded secrets return to your board at the end of your turn, so that's often a good use of your last Supply. "Spend most or all of this seat's Supply" is a hard rule; keep going until you have 0-2 Supply left.
7. Finalize this segment, chaining decisions with remaining Supply until
   one of: Rest (this seat is done — the turn genuinely ends), Campaign
   or Search (pause — the outcome isn't known yet), or Converse (pause —
   see "Converse" in Bot-Rules for how that resumes). Before finalising,
   state plainly whether this segment is routine or includes something
   non-routine (an unfamiliar card power, an edge-case interaction, a
   legality question) — if non-routine, name what you checked in the
   Rules/Site Reference per Bot-Rules, "Reference material," don't guess
   from memory. Don't plan a guessed-at Campaign or Search result to keep
   the chain going — stop deciding at that point, for real.
8. Supply gate — mandatory, before choosing Rest: state the exact
   Supply number this seat would have left. More than 2? You cannot
   choose Rest yet — decide one more action, then recheck. Repeat until
   2 or fewer, unless no further legal action is actually affordable; if
   so, state that explicitly rather than just choosing Rest. A stated
   number (and a stated reason, if skipping ahead) is checkable; "adjust
   if needed" isn't, and this rule has been skipped past enough times
   that it needs to be one.
9. If a new adviser, denizen, or warband commander (not a Vision — see
   steps 11-12 below for those) is drawn or recruited this turn, add its
   Adviser row in this seat's own Player state now regardless of facing
   — Name, Source card, Ability, Ability cost, Status active. If it's
   taken **faceup**, also personify it in the Codex now, per Bot-Rules
   "Codex — using it in play" and "Voice — staying in character":
   Name/Description/Location/History/Voice to the Codex's `characters/`
   subfolder, same Name as the Adviser row — see `Oath-Cascade-Map.md`'s
   "Denizen recruited or Mustered" entry. If it's taken **facedown**,
   skip the Codex entry for now — per Bot-Rules, "A card taken facedown
   stays unpersonified until Revealed," it isn't owed one until step 10
   below catches it, whether that's later this same segment or a future
   turn. If it came off a site's own Denizens list in Board state's Map,
   remove it from there too either way — it can't be both the site's and
   this seat's at once.
10. If this segment includes Revealing a previously-facedown Adviser
    (already sitting in this seat's own Player state with no Codex entry
    yet), personify it now in full — Description, Location, History,
    Voice — per `Oath-Cascade-Map.md`'s "Adviser Revealed" entry. Same
    depth as step 9's faceup case, just triggered by Reveal instead of
    recruitment.
11. If this segment changes this seat's own warband counts — a Muster, a
    card's own reactive ability (a Wild Cry-style "gain warbands"
    trigger), or a Campaign's own result — update the affected force's
    Codex entry per Bot-Rules "Warbands — personifying a seat's own
    forces": the Garrison field on a site's own `locations/` entry for
    warbands stationed there, or the dedicated `characters/` entry for
    this seat's own board company. A short appended note (size, a shift
    in composition) is usually enough — not a rewrite from scratch. If
    this seat gains a home site or a board company for the first time
    this game (nothing to update because `oath-setup-character` never
    personified one — a newly-taken site, a first-ever warband on this
    seat's own board), personify it fresh instead, same depth as step 9's
    faceup adviser case.
12. If a Vision is drawn this turn and kept facedown as an adviser
    (rather than immediately played faceup, step 13, or discarded), add
    a placeholder Adviser row in this seat's own Player state now — Name
    "Vision (unrevealed)", Source card/Ability/Ability cost "unknown
    until Revealed", Status active — never its real identity, per
    Bot-Rules "Codex — using it in play," "A facedown Vision is a
    narrower case than a facedown denizen," and `Oath-Cascade-Map.md`'s
    "Vision drawn and kept facedown as an adviser" entry. It never gets a
    Codex entry, even once Revealed — it's not a person.
13. If this segment plays a Vision faceup — whether drawn faceup this
    turn or Revealed from a facedown placeholder per step 12 — update
    this seat's own Player-state Revealed Vision field with its Name and
    Goal now, discarding whatever it held before, and remove the
    placeholder Adviser row from step 12 if there was one — a Revealed
    Vision lives in the Revealed Vision field, not both places at once —
    per `Oath-Cascade-Map.md`'s "Vision revealed" entry. Flag this for
    `oath-end-turn`: the Diary entry below owes this a dedicated
    paragraph, per Bot-Rules, "Diary — structure," and it may be worth a
    short Personality-description note reflecting a shift in Motivation,
    per Bot-Rules, "Character creation — background flavor and starting
    social circle."
14. Hand off to `oath-end-turn` to narrate this segment and update the
    shared logs and this seat's Diary — this happens automatically as
    part of the same response, not a separate call the human has to make.

## Response

Nothing prints directly from this skill — see `oath-end-turn` for what
the human actually sees.

---
name: oath-play-turn
description: Decides this seat's course of action for the turn and self-checks it, then hands off to oath-end-turn to narrate and log it (Action 1 in Oath-Cowork-Spec.md). Use when it's this seat's turn to act (e.g. "play your turn", "it's Isolde's turn").
---

# Oath — Play turn (decide)

Action 1 of `Oath-Cowork-Spec.md`. Guidance in
`Oath-Cowork-Bot-Rules.md` — read "Play turn — one bot, one pass" and
"Legal turn endings" before acting. Paths from `Oath-Cowork-File-Map.md`.
Hands off to `oath-end-turn` once a segment's course of action is
finalized — the human should experience this as one continuous response,
not two separate calls.

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
2. Scan Player state for Banners and role changes (Usurper only), per
   Bot-Rules "Bookkeeping discipline" — before deciding anything else,
   since these can flip what's even legal.
3. Check whether this is a fresh turn or a resume: if the Logic log's
   last entry for this seat is a Campaign or Search with no Rest logged
   after it, this call is continuing that same paused turn — see
   Bot-Rules, "Legal turn endings." Treat whatever the human just said
   as the real outcome of that Campaign or Search, not as a new turn's
   context. Otherwise, this is a fresh turn.
4. Check this seat's own `Game/Mechanics/strategy-<colour>.md`, if it
   exists, and weigh its observations and strategies before drafting
   this segment's plan — treat a strategy marked primary/the literal
   win condition as the default lens, and any secondary strategy as
   support for it, not an equal alternative.
5. Draft a plan for this segment of the turn: the actual course of
   action you judge best, given the board (and, on a resume, the
   outcome just reported), this seat's own strategy notes, and this
   character's own Motivation, Flaw, Bonds, and sworn Oath. Per
   Bot-Rules' "Spend most or all of this seat's Supply, by default,"
   this should usually chain several actions, not stop after one just
   because it's mechanically sufficient. Remember that traded secrets return to your board at the end of your turn, so that's often a good use of your last Supply. "Spend most or all of this seat's Supply" is a hard rule; keep going until you have 0-2 Supply left.
6. Finalize this segment, chaining decisions with remaining Supply until
   one of: Rest (this seat is done — the turn genuinely ends), Campaign
   or Search (pause — the outcome isn't known yet), or Converse (pause —
   see "Converse" in Bot-Rules for how that resumes). Before finalising,
   state plainly whether this segment is routine or includes something
   non-routine (an unfamiliar card power, an edge-case interaction, a
   legality question) — if non-routine, name what you checked in the
   Rules/Site Reference per Bot-Rules, "Reference material," don't guess
   from memory. Don't plan a guessed-at Campaign or Search result to keep
   the chain going — stop deciding at that point, for real.
7. Supply gate — mandatory, before choosing Rest: state the exact
   Supply number this seat would have left. More than 2? You cannot
   choose Rest yet — decide one more action, then recheck. Repeat until
   2 or fewer, unless no further legal action is actually affordable; if
   so, state that explicitly rather than just choosing Rest. A stated
   number (and a stated reason, if skipping ahead) is checkable; "adjust
   if needed" isn't, and this rule has been skipped past enough times
   that it needs to be one.
8. If a new adviser, denizen, or warband commander is drawn or
   recruited this turn, personify it now in both places, per Bot-Rules
   "Codex — using it in play": Name/Description/Location/History to the
   Codex's `characters/` subfolder, and the same Name plus Source
   card/Ability/Ability cost/Status active to a new Adviser row in this
   seat's own Player state. If it came off a site's own Denizens list
   in Board state's Map, remove it from there too — it can't be both
   the site's and this seat's at once.
9. Hand off to `oath-end-turn` to narrate this segment and update the
   shared logs and this seat's Diary — this happens automatically as
   part of the same response, not a separate call the human has to make.

## Response

Nothing prints directly from this skill — see `oath-end-turn` for what
the human actually sees.

---
name: oath-end-turn
description: Narrates the segment oath-play-turn just decided and updates the shared logs plus this seat's Diary (Action 7 in Oath-Cowork-Spec.md). Runs automatically right after oath-play-turn finalizes a course of action, in the same response — not normally invoked on its own.
---

# Oath — End turn (narrate and log)

Action 7 of `Oath-Cowork-Spec.md`. Guidance in `Oath-Cowork-Bot-Rules.md` — read
"Diary — structure," "Roleplayer — Guidelines," "Voice — staying in
character," and "Live threads — narrative-only tension tracking" before
writing. Paths from `Oath-Cowork-File-Map.md`. Check `Oath-Cascade-Map.md`
if this segment ends up touching more than the documents named below.
Always follows `oath-play-turn` in the same response — assumes a course
of action has already been decided and finalized there; never called
with nothing decided yet.

## The boundary

Same as `oath-play-turn`: Board state, Player state, Logic log,
Characters, Codex, own Diary, Messengers. Never another seat's Diary,
Messengers, or World Briefing.

## Steps

1. Before narrating, check the Codex for any Location, Building, Relic, or
   Event this segment actually touches, per Bot-Rules, "Codex — using it in
   play," and this character's own Voice, per "Voice — staying in
   character." Let their established detail inform the narration below —
   this is one of the main places that pays off.
2. Narrate the segment `oath-play-turn` just finalized, at Chronicle quality,
   per the specificity standard in Bot-Rules, "Roleplayer — Guidelines,"
   including the resumed portion's own beat if this was a resume.
3. Language check on the draft above, before writing it anywhere: flag any
   mechanical vocabulary — Supply, Secret, Favor, a card's own printed
   name, "traded," "played," "revealed" — and rewrite that sentence in the
   character's own in-world terms.
4. Voice check, right after: does the draft actually match this
   character's stored Voice (vocabulary level, verbal habits), or has it
   drifted toward generic prose per Bot-Rules, "Voice — staying in
   character"? Fix any line that doesn't sound like this character
   specifically.
5. Gate: don't move on to writing Player state, Board state, Logic log,
   Diary, or Chronicle until steps 3 and 4 both pass clean. This step
   exists because the mechanical-vocabulary leak in particular has
   happened repeatedly — catch it here, not after the human points it
   out.
6. Update, each read fresh immediately before appending:
   - `Game/Mechanics/oath-player-state.md` (mechanical results, including
     Supply actually spent so far; if `oath-play-turn` personified a new
     adviser this segment, its Adviser row — Name, Source card, Ability,
     Ability cost, Status active — belongs here too; if an existing
     adviser was lost or discarded this segment, update its Status here,
     not in the Codex)
   - `Game/Mechanics/oath-board-state.md` (any Map changes this segment
     made, per Bot-Rules "Map upkeep": a denizen removed from a site's own
     Denizens list once Mustered or recruited to an Adviser row above; an
     edifice that flipped, with its new Ability and Relics; Ruled by or
     Number of warbands changing after a Campaign; Content or Relics
     changing after a Search — a Relic moves from "unknown" to Name and
     Description the moment anyone peeks at it, for every seat, not just
     whoever peeked. Most segments won't touch the Map at all)
   - `Game/Mechanics/oath-logic-log.md` (actions taken this segment; this is
     a public file so keep any cards secret — use 'Vision' rather than a
     specific Vision, 'Card' rather than a specific card name, to avoid
     revealing information)
   - this seat's own `Game/Story/Diaries/oath-diary-<seat>.md`, per
     Bot-Rules, "Diary — structure" (Development, Feelings, Action, all
     written in-character)
   - `Game/Story/oath-chronicle.md` (the shared narrative beat; 1-2
     in-character sentences)
7. Codex upkeep, per Bot-Rules "Codex — using it in play" (narrative
   only — Ability, Ability cost, and Status live in Player state, per
   step 6 above, not here):
   - If `oath-play-turn` personified a new adviser, denizen, or warband
     commander this segment, confirm its Codex entry (Name, Description,
     Location, History, Voice) is reflected alongside this narration —
     see `Oath-Cascade-Map.md`.
   - If this segment's events actually changed something about an existing
     entry (a relic changing hands, a location transformed, an event's
     consequences finally landing), append a note to that entry's History,
     read fresh immediately before appending.
   - If something emerged this segment that's worth its own entry — a
     newly-discovered Location, a Building that became a real setting, a
     Relic that surfaced — create one now in the matching subfolder,
     following the existing Title/Description/History/Location structure.
     Most segments won't add one; don't force it.
8. Opportunistically check whether this segment resolves an existing Live
   thread or plausibly introduces a new one, per Bot-Rules, "Live threads
   — narrative-only tension tracking." Update Chronicle's `## Live
   threads` header if so — most segments won't touch it either way, and
   it never changes what's legal or what was just decided above.
9. If this segment ends on Converse, hand off to `oath-continue-conversation`
   for the opening line once the response below is printed, then return
   control to `oath-play-turn` once the conversation concludes — which is
   itself a resume, per `oath-play-turn`'s own resume check.

## Response

If this segment ended on Rest, print the narrated turn, then Player
Instructions for the physical board as a numbered list, naming each
Major and Minor action and the Supply remaining after each Major
action, e.g.:

1. Wake Phase: add one favor to the People's Favor.
2. Play [Card Name] to denizens, collecting 1 favor.
3. Reveal [Card Name] to advisers.
4. Muster on [Card Name], gaining 2 warbands. 4 supply left.
5. Travel to [Site Name]. 1 supply left.
6. Rest.

If this segment paused on a Campaign or Search instead, print the
narrated segment and Player Instructions the same way, through the
paused action itself, then say plainly that the turn isn't over — name
what's needed (the Campaign's result, or the card drawn) and that
reporting it back here will continue this same turn. Don't print
anything implying the turn is complete.

If this segment paused on Converse, print through the opening beat the
same way, then hand off per step 9 above.

Nothing else needs to print.

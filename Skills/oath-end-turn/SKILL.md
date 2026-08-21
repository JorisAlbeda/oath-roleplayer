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
4. Voice and device check, right after: does the draft actually match
   this character's stored Voice (vocabulary level, verbal habits), or
   has it drifted toward generic prose, per Bot-Rules, "Voice — staying
   in character"? And separately, does it stay inside "Roleplayer —
   Guidelines" own rhetorical-device budget — at most one reversal,
   comparison, or negation-stacked beat per character's turn, most turns
   at zero? Fix any line that doesn't sound like this character
   specifically, and cut back any turn that's spent more than its one
   device.
5. Gate: don't move on to writing Player state, Board state, Logic log,
   Diary, Chronicle, or any Codex prose (step 7 below) until steps 3 and
   4 both pass clean. This step exists because the mechanical-vocabulary
   leak in particular has happened repeatedly — catch it here, not after
   the human points it out. Codex is included deliberately: it's easy to
   assume a clean Diary means the check is done for this segment, but
   Codex Description/History is separate prose, written fresh in step 7,
   and needs the same pass — "Round 0," a card's own printed name, or
   "this seat's starting adviser" are exactly the kind of phrase that
   survives here if it's not re-checked.
6. Update, each read fresh immediately before appending:
   - `Game/Mechanics/oath-player-state.md` (mechanical results, including
     Supply actually spent so far; if `oath-play-turn` recruited a new
     adviser this segment, its Adviser row — Name, Source card, Ability,
     Ability cost, Status active — belongs here too, regardless of
     facing; if an existing adviser was lost or discarded this segment,
     update its Status here, not in the Codex; if this segment drew a
     Vision and kept it facedown, a placeholder Adviser row instead —
     Name "Vision (unrevealed)", Source card/Ability/Ability cost
     "unknown until Revealed" — never its real identity, per
     `Oath-Cascade-Map.md`'s "Vision drawn and kept facedown as an
     adviser" entry; if this segment played a Vision faceup instead, its
     Revealed Vision field — Name and Goal, discarding whatever it held
     before, and removing any facedown placeholder row rather than
     leaving both — per `Oath-Cascade-Map.md`'s "Vision revealed" entry;
     Warbands in reserve, whenever a Muster, Kill, or other gain/loss
     changed it this segment; and if this segment ended on Rest, the
     Supply refresh itself, computed from Bot-Rules' "Warband reserve
     and the Supply refresh table," not flagged for the human to confirm)
   - `Game/Mechanics/oath-board-state.md` (any Map changes this segment
     made, per Bot-Rules "Map upkeep": a denizen removed from a site's own
     Denizens list once Mustered or recruited to an Adviser row above; an
     edifice that flipped, with its new Ability and Relics; Ruled by or
     Number of warbands changing after a Campaign; Content or Relics
     changing after a Search — a Relic moves from "unknown" to Name and
     Description the moment anyone peeks at it, for every seat, not just
     whoever peeked; Favor Banks, whenever favor moved to or from one;
     Discard Pile counts, remembering discards land on the _next_ Region
     clockwise, not the acting pawn's own. Most segments won't touch the
     Map at all)
   - `Game/Mechanics/oath-logic-log.md` (actions taken this segment; this is
     a public file so keep any cards secret — use 'Vision' rather than a
     specific Vision, 'Card' rather than a specific card name, to avoid
     revealing information)
   - this seat's own `Game/Story/Diaries/oath-diary-<seat>.md`, per
     Bot-Rules, "Diary — structure" (Development, Feelings, Action, all
     written in-character; if this segment played a Vision faceup, add
     the dedicated paragraph Bot-Rules calls for there, beyond the usual
     three)
   - `Game/Story/oath-chronicle.md` (the shared narrative beat; 1-2
     in-character sentences)
7. Codex upkeep, per Bot-Rules "Codex — using it in play" (narrative
   only — Ability, Ability cost, and Status live in Player state, per
   step 6 above, not here). Run this prose through the same steps 3-4
   check before it's written, per the gate above — a card's own printed
   name, "Round 0," "this seat's starting adviser," and similar phrases
   belong in Player state and Logic log, never in Codex prose. Description
   and History are an in-world biography, not a record of when or how this
   segment recruited them: give a new character an actual life before this
   seat ever met them — a trade, a family, a loss, a reason they know what
   they know — the same depth Bot-Rules already expects of a Background
   Flavor at character creation, not a one-line stub pointing back at this
   turn:
   - If `oath-play-turn` recruited a new adviser, denizen, or warband
     commander **faceup** this segment, or Revealed a previously-facedown
     one, confirm its Codex entry (Name, Description, Location, History,
     Voice) is reflected alongside this narration — see
     `Oath-Cascade-Map.md`'s "Denizen recruited or Mustered" and "Adviser
     Revealed" entries. If it was taken facedown and not Revealed this
     segment, there's nothing to reflect yet — that's expected, not a gap.
     A Vision, facedown or Revealed, never gets a Codex entry either way
     — it's not a person, so there's nothing here to confirm for it.
   - If this segment's events actually changed something about an existing
     entry (a relic changing hands, a location transformed, an event's
     consequences finally landing), append a note to that entry's History,
     read fresh immediately before appending.
   - If something emerged this segment that's worth its own entry — a
     newly-discovered Location, a Building that became a real setting, a
     Relic that surfaced — create one now in the matching subfolder,
     following the existing Title/Description/History/Location structure.
     Most segments won't add one; don't force it.
   - If this segment's Muster or Campaign made a site's own garrison
     worth naming or updating (a new force raised, or the site handed to
     an entirely new ruler), personify or update its Codex `locations/`
     entry's Garrison field now, per Bot-Rules, "Warbands — personifying
     the garrison," and `Oath-Cascade-Map.md`'s "A site's garrison
     personified or updated" entry. Most Map changes won't warrant this;
     don't force it.
8. If this seat's own Role genuinely changed this segment (Usurper flip,
   Citizenship offered or accepted, a Citizen exiled back out), or this
   segment played a Vision faceup, append a short note to Personality
   description in `Game/Story/oath-characters.md` reflecting the shift
   in Motivation, per Bot-Rules, "Character creation — background
   flavor and starting social circle" — the same restraint already used
   for Bonds in `oath-conclude-conversation`: only when it actually
   shifted, not on every turn. Read the file fresh immediately before
   appending.
9. Opportunistically check whether this segment resolves an existing Live
   thread or plausibly introduces a new one, per Bot-Rules, "Live threads
   — narrative-only tension tracking." Update Chronicle's `## Live
threads` header if so — most segments won't touch it either way, and
   it never changes what's legal or what was just decided above.
10. If this segment ends on Converse, hand off to `oath-continue-conversation`
    for the opening line once the response below is printed, then return
    control to `oath-play-turn` once the conversation concludes — which is
    itself a resume, per `oath-play-turn`'s own resume check.

## Response

Report what was corrected.

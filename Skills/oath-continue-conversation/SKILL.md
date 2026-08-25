---
name: oath-continue-conversation
description: Adds one reply line to an in-progress cross-seat dialogue (Action 4 in Oath-Cowork-Spec.md). Use when the user wants a character to respond in an ongoing conversation (e.g. "have Lyn reply", "continue the Dorcas-Lyn conversation"). Call this alternately on each side's seat until one of them ends it or the human calls oath-conclude-conversation directly.
---

# Oath — Continue conversation

Action 4 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
Guidance in `Oath-Cowork-Bot-Rules.md`, "Roleplayer — Guidelines" and
"Voice — staying in character" — read both sections in full, from that
file itself, before the first reply in any conversation this bot
hasn't already loaded them for this session. A citation to a section
name is not a substitute for reading it; if the fetch for
`Oath-Cowork-Bot-Rules.md` fails, that's a Required pre-flight gap
(Bot-Rules, "Pre-flight check — required vs recommended") — don't
fall back to writing from this skill's own summary of the rules below
without saying so plainly first.

## The boundary

Read this seat's own `Game/Story/oath-characters.md` entry, this
character's own Codex entry (including Voice) and any Regional voice
notes on their location, the oath-chronicle in full, and this
seat's own Diary's — once per conversation, on the
first reply only, not on every call (see step 3). The Converse dialogue
file is the one exception: read it fresh, in full, on every single
call, since it's append-only and the other seat's bot may have written
to it since your last turn. Never another seat's Diary, Messengers, or
World Briefing, and never Board state or Logic log.

## Steps

1. Take the Converse dialogue file (e.g.
   `Game/Story/Conversation logs/oath-conversation-dorcas-lyn-R2-1.md`)
   as given.
2. Read it in full so far, fresh — every call, even if you read it
   minutes ago in this same session.
3. First reply in this conversation: read this seat's own Characters
   entry, Codex entry (including Voice), the oath-chronicle in full,
   and this seat's own Diary. State
   plainly that you did. On every later reply in the same conversation,
   skip this and say so — unless the dialogue has just touched a
   Location, Relic, or Event you haven't grounded yet, in which case
   check only that one thing in the Codex, per Bot-Rules, "Codex — using
   it in play." If Voice doesn't exist yet on an older Codex entry, add
   it now, this is as natural a moment as any. Run the mechanical
   vagueness scan from step 4 against that entry right now, not just
   against the drafted line later — if it's vague on a detail this line
   needs — how a price is paid, what a ritual involves, what a cost
   actually feels like, why something happened, what a place looks
   like — that's a required stop per Bot-Rules, "Not knowing is not an
   excuse — invent it": invent the specific version now, state the scan
   result plainly ("entry unspecified on [detail] — invented: ..."),
   and append it to the entry before finishing this turn rather than
   writing around the gap.
4. Before drafting the line, run these checks in order, per Bot-Rules,
   "Roleplayer — Guidelines." (b) Urgency, the standing-want check
   folded into it, and (c) Tactic get stated explicitly in the
   response, per the Gate below — silent is fine for (a), (d), and
   (e), but the result of each of those still has to be nameable if
   asked, not just felt:
   a. **Understanding.** Name plainly what the other side's last line
   in the file actually said — the literal words, not the most
   dramatic reading. If this character wouldn't actually follow it
   as written, let that show (a direct question, a flat admission
   of not following) instead of inventing a bridge.
   b. **Urgency.** Name the single highest-stakes fact this character
   already has in hand — from this seat's Diary, Codex, the
   Chronicle, or something witnessed earlier in this same
   conversation — that makes this exchange matter _now_. A line
   written without one in hand defaults to the safest, smallest
   version of the ask; that's the failure mode this check exists to
   catch. Alongside it, name this character's single strongest want
   per Bot-Rules, "A standing want left untouched for a full turn is
   a failure, not restraint," and say plainly whether this line
   pursues it, states it outright, or explicitly defers it. Check
   the file read in step 2 for how many turns, by this character,
   have passed since that want was last pursued, named, or
   deferred — one untouched turn is the most this line is allowed to
   let stand; if the last turn already let it pass untouched, this
   line must address it, full stop, not just note the gap and move
   on.
   c. **Tactic.** Work out this character's want this beat, their
   tactic for getting it, and what they do if the tactic fails. A
   line whose only job is conveying true, relevant information —
   even information that matters — gets recast as an attack,
   deflection, extraction, dare, or closing move, not delivered as
   a report.
   d. **Composure.** If this character's own tactic from a prior line
   in this same conversation has just failed, let their control
   crack rather than defaulting to staying rhetorically
   self-possessed — even where it costs some strict adherence to
   their stated Voice.
   e. **Silence.** If the honest answer to (a)-(d) is that this
   character can't actually manage a full reply right now, let the
   gap show — a pause, a truncated line, a single word — rather
   than narrating that they couldn't find the words, and rather
   than padding the reply out to something longer than the moment
   earns.

   Then add exactly one reply, checked against this character's stored
   Voice (vocabulary level, verbal habits, speech rhythm), same
   specificity standard as any other narration. This is one line in an
   ongoing back-and-forth, not a full scene. Per Bot-Rules, "Say what
   you want to say, then stop — length is never a target": let this
   reply be exactly as long as what this character actually needs to
   say or do this beat, not a length decided in advance — a single
   short sentence when that's the honest answer, several sentences when
   there's a real beat's worth of tactic, reaction, and stakes actually
   happening. Padding it out to seem thorough, or clipping it short to
   seem economical, are both the wrong move for the same reason: the
   content should decide the length, not the other way around.

   Before finalizing it, check the rhetorical-device budget per
   Bot-Rules, "Rhetorical devices are spent, not banned" — and check it
   against the _whole file read in step 2_, not just this reply in
   isolation. The scene-wide cap (one reversal/comparison/negation-
   stacked beat for the entire conversation) is tighter than the
   per-turn one and governs regardless of whose line spent it — if any
   earlier line in the file, by any character, already used one, this
   reply gets zero, full stop, even though its own per-turn cap would
   otherwise allow one. Scan every prior line for the device shapes
   named there before writing, not just the line immediately above this
   reply — the cap is cumulative across the whole file, not a
   look-one-line-back check.

   **Run this as a mechanical scan of the drafted line, not a holistic
   judgment call.** Experimentation found that a
   bot is measurably worse at recognizing one of these devices in a
   line it just wrote than in a line someone else wrote — so don't ask
   "does this feel like a reversal." Instead, reread the exact drafted
   line, word by word, hunting only for these concrete tells:
   - two or more of not / n't / never / nothing / nobody / no-one
     landing inside the same beat (one sentence, or one clause tied to
     the same action or line of dialogue) — a negation-stacked beat,
     regardless of how natural each one sounds alone;
   - a comparison marker — "the way," "like," "as if," "as though" —
     used to describe an action, feeling, or gesture, rather than an
     actual simile a character would say aloud;
   - a "not X, [comma or period] Y" or "X, not Y" contrast shape, in
     either order, in any wording, not just the exact phrasing of any
     example given elsewhere;
   - a controlled-affect word used to tag how a line is delivered —
     "flat," "level," "quiet," "even," "steady," "measured," "calm,"
     "cool," "muted," or a clear equivalent — per Bot-Rules' ban on
     this category. Unlike the three shapes above, this one isn't a
     scene-wide budget of one: it's an outright ban, every hit counts
     against the line regardless of whether the budget above has
     already been spent, and the fix isn't to cut the word but to
     replace it with the character's actual, specific emotional state
     and let that state push the line toward something bigger or
     riskier, not smaller.

   List every hit this scan turns up — including a borderline one you'd
   otherwise be tempted to argue away — before ruling on whether it
   counts as this turn's one allowed spend or pushes the turn over
   budget. A hit named and then judged not to count still gets named;
   silently deciding it doesn't count is the failure this scan exists
   to catch. If the scan turns up nothing, say that plainly too — "scan:
   no hits" is itself part of the visible trace, not an assumed default.

   **Run a second, separate mechanical scan for vagueness, per
   Bot-Rules, "Not knowing is not an excuse — invent it."** This isn't
   limited to relic mechanisms — it fires on any detail this line
   states or alludes to that this bot doesn't actually have on record:
   how a price is paid, why a character did something, what a place
   looks like, what's in a letter, a name for someone who could be
   named. This is a different failure from the device scan above and
   doesn't share its budget — a line can pass the device scan clean and
   still be vague, and a vague line doesn't get a free pass just
   because nothing else fired. Reread the drafted line hunting only for
   these tells:
   - a euphemism standing in for a detail that's actually unknown —
     "paid it," "gave it what it wanted," "did what it asked," "in his
     own way," "whatever it took," "answered the call," "for reasons of
     his own," "something about," or a clear equivalent;
   - a hedge word doing the same job — "somehow," "some kind of," "some
     way," "a sort of," "a certain";
   - an unnamed placeholder where a name or detail could be invented
     instead — "someone," "some village," "a man," with nothing in the
     line explaining why this character wouldn't know or use the
     specific version;
   - a sentence naming a cost, ritual, reason, place, or event with no
     named object, sensation, number, or consequence anywhere in it.

   Apply the paste-test on anything borderline: could this exact
   sentence be pasted into a completely different scene — a different
   relic, a different character's reason, a different place — without
   changing a word? If yes, it's vague regardless of how natural it
   reads. A hit means stop — don't append the line yet — invent one
   concrete, sensory, testable detail on the spot per step 3, and
   rewrite the line around it before it ships. List every hit (or
   "vagueness scan: no hits") the same way the device scan above does.

   **Gate:** don't append anything until (a)-(e) above, the
   device-budget scan, and the vagueness scan all pass clean. Appending
   the line isn't enough on its own — state, in the response to the
   user, which highest-stakes fact, which standing want and how it's
   being handled, and which tactic this line is actually built on (per
   (b) and (c)), and print both scans' own hit lists (or "no hits") for
   this line, the same way the rest of the gate already has to be
   stated explicitly. A check that only happens silently, with no
   visible trace, is indistinguishable from a check that didn't happen
   at all — this is exactly the gap that let a negation-stack and a
   comparison both through in the same turn once, under this same
   instruction, before the device scan step existed.

   Append it as the next line at the very end of the file, then print
   it in the response to the user so they can follow along.

5. Optionally end it here if this character has nothing more to say —
   say so plainly rather than padding out a reply.

## Response

Print the line just added, along with the one-line statement of stakes
and tactic called for in step 4's gate, and both scans' hit lists (or
"no hits") for this line — the device scan and the vagueness scan. If
this character ended it, say so — the human should call
oath-conclude-conversation next either way.

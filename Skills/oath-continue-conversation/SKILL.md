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
   it now, this is as natural a moment as any.
4. Before drafting the line, run these checks in order, per Bot-Rules,
   "Roleplayer — Guidelines." (b) Urgency and (c) Tactic get stated
   explicitly in the response, per the Gate below — silent is fine for
   (a), (d), and (e), but the result of each of those still has to be
   nameable if asked, not just felt:
   a. **Understanding.** Name plainly what the other side's last line
      in the file actually said — the literal words, not the most
      dramatic reading. If this character wouldn't actually follow it
      as written, let that show (a direct question, a flat admission
      of not following) instead of inventing a bridge.
   b. **Urgency.** Name the single highest-stakes fact this character
      already has in hand — from this seat's Diary, Codex, the
      Chronicle, or something witnessed earlier in this same
      conversation — that makes this exchange matter *now*. A line
      written without one in hand defaults to the safest, smallest
      version of the ask; that's the failure mode this check exists to
      catch.
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
   ongoing back-and-forth, not a full scene.

   Before finalizing it, check the rhetorical-device budget per
   Bot-Rules, "Rhetorical devices are spent, not banned" — and check it
   against the *whole file read in step 2*, not just this reply in
   isolation. The scene-wide cap (one reversal/comparison/negation-
   stacked beat for the entire conversation) is tighter than the
   per-turn one and governs regardless of whose line spent it — if any
   earlier line in the file, by any character, already used one, this
   reply gets zero, full stop, even though its own per-turn cap would
   otherwise allow one. Scan every prior line for the device shapes
   named there before writing, not just the line immediately above this
   reply — the cap is cumulative across the whole file, not a
   look-one-line-back check.

   **Gate:** don't append anything until (a)-(e) above and the
   device-budget check both pass clean. Appending the line isn't
   enough on its own — state, in the response to the user, which
   highest-stakes fact and which tactic this line is actually built on
   (per (b) and (c)), the same way the device-budget spend already gets
   stated explicitly. A check that only happens silently, with no
   visible trace, is indistinguishable from a check that didn't happen
   at all.

   Append it as the next line at the very end of the file, then print
   it in the response to the user so they can follow along.
5. Optionally end it here if this character has nothing more to say —
   say so plainly rather than padding out a reply.

## Response

Print the line just added, along with the one-line statement of stakes
and tactic called for in step 4's gate. If this character ended it, say
so — the human should call oath-conclude-conversation next either way.

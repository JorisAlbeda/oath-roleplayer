---
name: oath-continue-conversation
description: Adds one reply line to an in-progress cross-seat dialogue (Action 4 in Oath-Cowork-Spec.md). Use when the user wants a character to respond in an ongoing conversation (e.g. "have Lyn reply", "continue the Dorcas-Lyn conversation"). Call this alternately on each side's seat until one of them ends it or the human calls oath-conclude-conversation directly.
---

# Oath — Continue conversation

Action 4 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.

## The boundary

Read only this seat's own `Game/Story/oath-characters.md` entry, the
Codex, the Converse dialogue file, and this seat's own Diary for voice
consistency. Never another seat's Diary, Messengers, or
World Briefing, and never Board state or Logic log.

## Steps

1. Take the Converse dialogue file (e.g.
   `Game/Story/Conversation logs/oath-conversation-dorcas-lyn-R2-1.md`)
   as given.
2. Read it in full so far, fresh.
3. Check the Codex for anything the conversation actually touches — a
   shared Location, a Relic being discussed, a past Event referenced —
   per Bot-Rules, "Codex — using it in play." Let its established detail
   ground this reply rather than leaving it generic.
4. Add exactly one reply, in this character's voice, same specificity
   standard as any other narration (Bot-Rules.md, "Roleplayer —
   Guidelines"). This is one line in an ongoing back-and-forth, not a
   full scene. Append it as the next line at the very end of the file.
5. Optionally end it here if this character has nothing more to say —
   say so plainly rather than padding out a reply.

## Response

Print the line just added. If this character ended it, say so — the
human should call oath-conclude-conversation next either way.

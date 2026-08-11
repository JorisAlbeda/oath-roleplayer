---
name: oath-continue-conversation
description: Adds one reply line to an in-progress cross-seat dialogue (Action 4 in Oath-Cowork-Spec.md). Use when the user wants a character to respond in an ongoing conversation (e.g. "have Lyn reply", "continue the Dorcas-Lyn conversation"). Call this alternately on each side's seat until one of them ends it or the human calls oath-conclude-conversation directly.
---

# Oath — Continue conversation

Action 4 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.
Guidance in `Oath-Cowork-Bot-Rules.md`, "Voice — staying in character."

## The boundary

Read this seat's own `Game/Story/oath-characters.md` entry, this
character's own Codex entry (including Voice) and any Regional voice
notes on their location, the oath-chronicle's Live threads, and this
seat's own Diary's most recent entries — once per conversation, on the
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
   entry, Codex entry (including Voice), the oath-chronicle's Live
   threads, and this seat's own Diary's most recent entries. State
   plainly that you did. On every later reply in the same conversation,
   skip this and say so — unless the dialogue has just touched a
   Location, Relic, or Event you haven't grounded yet, in which case
   check only that one thing in the Codex, per Bot-Rules, "Codex — using
   it in play." If Voice doesn't exist yet on an older Codex entry, add
   it now, this is as natural a moment as any.
4. Add exactly one reply, checked against this character's stored Voice
   (vocabulary level, verbal habits, speech rhythm), same specificity
   standard as any other narration (Bot-Rules.md, "Roleplayer —
   Guidelines"). This is one line in an ongoing back-and-forth, not a
   full scene. Append it as the next line at the very end of the file.
5. Optionally end it here if this character has nothing more to say —
   say so plainly rather than padding out a reply.

## Response

Print the line just added. If this character ended it, say so — the
human should call oath-conclude-conversation next either way.

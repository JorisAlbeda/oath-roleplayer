---
name: oath-conclude-conversation
description: Closes out a cross-seat dialogue and folds its outcome into the shared story (Action 5 in Oath-Cowork-Spec.md). Use when a character has ended a conversation, or the user decides to cut it off (e.g. "wrap up the Dorcas-Lyn conversation", "conclude that conversation").
---

# Oath — Conclude conversation

Action 5 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`.

## The boundary

Read the Converse dialogue file, both participants' Diary
entries, the Codex, and `Game/Story/oath-characters.md`. Never Board state,
Logic log, or another seat's Messengers/World Briefing.

## Steps

1. Take the Converse dialogue file as given. Add a closing line if the
   last line didn't already end it — appended after it, never inserted
   earlier in the file. Same specificity standard as any other line.
2. Summarize the outcome in **both** participants' own Diaries —
   not just whoever initiated. Link to the Converse dialogue file itself
   rather than repeating it in full. Append each summary at the very end
   of its own file, reading it fresh immediately beforehand.
3. Only if the conversation happened somewhere another character could
   witness it: add a short beat to `Game/Story/oath-chronicle.md`,
   appended at the very end.
4. Only if the relationship actually shifted: update Bonds for the
   affected character(s) in `Game/Story/oath-characters.md`. Most
   conversations won't move it.
5. Codex upkeep, per Bot-Rules "Codex — using it in play": if the
   conversation changed something about an existing entry (a relic
   changing hands, a bond that redefines a place both characters share),
   append a note to that entry's History, read fresh immediately
   beforehand. If the conversation surfaced something new and significant
   enough to be worth its own entry, create one in the matching subfolder.
   Most conversations won't touch the Codex at all.
6. If this conversation was reached mid-turn (a seat ended their turn on
   Converse), return control to that seat's oath-play-turn so it can
   finish resolving the turn.

## Response

Print a short summary of how the conversation resolved and whether
anything changed (Bonds, Chronicle). Nothing else needs to print.

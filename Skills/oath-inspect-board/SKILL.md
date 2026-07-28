---
name: oath-inspect-board
description: Self-directed strategy check-in for this seat (Action 8 in Oath-Cowork-Spec.md) — reads Board state and Player state and writes this seat's updated strategy to its own strategy file. Use when the user asks for a strategy check, a board review, or to reassess the plan (e.g. "check the board", "review your strategy", "what's the plan now"). Replaces the old subagent adviser-consult with a self-check the bot runs on its own reasoning.
---

# Oath — Inspect board (self-check)

Action 8 of `Oath-Cowork-Spec.md`. Paths from `Oath-Cowork-File-Map.md`. Not
part of the Play turn / End turn chain — a standalone self-check this seat's
bot runs on its own strategic reasoning, replacing the old cross-seat
adviser-subagent consult. Run it whenever the human asks, or when
`oath-play-turn` finds this seat's strategy file stale or missing.

## The boundary

Read `Game/Mechanics/oath-board-state.md`,
`Game/Mechanics/oath-player-state.md`, and this seat's own
`Game/Mechanics/strategy-<colour>.md` if it exists. No board
photographs — Board state and Player state are kept current from the
Logic log after Game Setup's own initial ones, so there's nothing left
to reconcile against a photo. Never another seat's private documents or
strategy file.

## Steps

1. Read Board state and Player state, fresh.
2. Check this seat's own `Game/Mechanics/strategy-<colour>.md`, if it
   exists, and weigh its existing observations and strategy against the
   current board — is it still viable, or has something changed that
   undercuts it?
3. Make two observations about the board, one sentence each.
4. Devise a strategy for winning the game: three bullet points, one
   sentence each. This can confirm the existing strategy or replace it
   outright.
5. Write the two observations and the strategy to
   `Game/Mechanics/strategy-<colour>.md`, creating it if it doesn't exist
   yet. This file holds only this seat's current thinking, not a running
   history — overwrite it each time rather than appending.

## Response

Print the two observations and the strategy just written.

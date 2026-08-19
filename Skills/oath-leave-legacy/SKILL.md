---
name: oath-leave-legacy
description: Writes this seat's end-of-game legacy note (Game/Story/Legacy/legacy-<colour>.md) for this seat's own colour, giving a future game's bot of the same colour a narrative thread to build from — and closes out this seat's own departing Codex cast (Died year, past tense, moved to codex/characters/historical/). Use once the game has ended and the Chronicle phase has reshaped the board, when the user asks to "leave a legacy", "write the legacy file", "close out this character for next time", or similar. Run once per AI-controlled colour, in that colour's own chat.
---

# Oath — Leave legacy

Not one of the eight Actions in `Oath-Cowork-Spec.md` — a ninth,
end-of-game-only step, run after the Chronicle phase reshapes the board
between games. Paths from `Oath-Cowork-File-Map.md`.

## The boundary

Same as every other skill here: no Board state or Logic log beyond
what's needed for context, and never the Rules/Site Reference/action
summary. This step adds one narrow exception — the
`Board Photographs/Endgame-Before` and `Board Photographs/Endgame-After`
folders are fine to look at, but only for what's visibly different
between them (banners, tokens, a site's look), never to reconstruct or
state mechanical game state from them.

## Steps

1. Ask the human how much time will pass before the next game starts (a
   number of years). This resolves what would otherwise be a chicken-
   and-egg problem: the Died year for anyone closed out in step 7 below
   can be stamped immediately — this seat's own current Year, per
   `timeline.md`, plus the elapsed time given here — rather than left as
   a placeholder to fill in later.
2. Reread `Game/Story/oath-chronicle.md`'s final beats and this seat's
   own `Game/Story/Diaries/oath-diary-<seat>.md` in full,
   especially anything involving this character's most significant
   bond, rivalry, or unresolved thread with another character — and
   anything in the Codex (an adviser, denizen, or commander this
   character personified) that mattered enough to be worth carrying
   forward.
3. Look at every photo in `Board Photographs/Endgame-Before` and every
   photo in `Board Photographs/Endgame-After`, if they exist (if not, skip this step). Note what's visibly
   changed, especially near this character's own ground, if anything —
   don't interpret or state mechanical game state from either folder,
   just the physical look of things (a banner moved, a site's tokens
   cleared, and so on).
4. Write an in-world fragment left behind — a family record, an
   heirloom, an old debt, a reputation, or a rumor — grounded in at least one
   physical detail actually seen changing between the two folders, if
   this character's own ground shows one.
5. Keep it under 200 words, written as something a future character
   would actually possess or have heard, not a plot summary. Follow the
   specificity standard in `Oath-Cowork-Bot-Rules.md`, "Roleplayer —
   Guidelines," as always — including its rhetorical-device budget,
   which matters more here than almost anywhere else: at 200 words with
   no scene around it to dilute one, an overspent device is the whole
   piece's texture, not one beat among many.
6. `Game/Story/Legacy/legacy-<colour>.md` holds only this colour's most
   recent legacy, not a running family history. If the file already
   exists from an earlier game, read it fresh immediately before
   writing (never rely on an earlier read this conversation), then
   replace its contents entirely with this game's fragment, headed
   `## <Character Name>` — the previous entry doesn't carry forward
   once this one's written. If the file doesn't exist yet, create it
   with this as the only entry. This skill doesn't create or update a
   portrait image for the colour — see `oath-setup-character`, which
   only reads one if it already exists.
7. Close out this seat's own player character and its own advisers in
   the Codex — the other half of what step 1's elapsed time enables.
   For each one still `Active` in `codex/characters/`: decide, briefly,
   how the elapsed years from step 1 went for them, set Status to
   Deceased where applicable with a Died year (per Bot-Rules, "Dating a
   Codex entry"), add a sentence or two on what's remembered of them,
   and convert Description and History to past tense throughout. The
   one exception: a character with a specific in-world reason to
   persist across the boundary (long-lived or effectively immortal)
   skips this entirely and stays Active, present tense — default is
   close out, persistence is the deliberate exception, not the other
   way around.
8. Move each entry closed out in step 7 into
   `codex/characters/historical/` (per Bot-Rules, "Codex — using it in
   play," "Current vs. historical") — the folder move and the narrative
   closure happen in the same pass, not as separate steps. A character
   kept under the persistence exception stays in `characters/`.
9. Leftover cast not clearly owned by this seat — companions or NPCs
   this character interacted with but didn't personify as its own
   adviser — aren't this skill's job to close out. Flag them in this
   skill's own Response for whichever human player is doing the wider
   sweep across all seats, rather than guessing at cast that isn't this
   colour's own.

## Response

Print the legacy entry just written (step 6), and a short list of which
Codex entries this pass closed out and moved to `historical/` (steps
7-8) — plus any leftover cast flagged in step 9 for a wider sweep — so
the human can confirm all of it before the next game starts.

---
name: oath-leave-legacy
description: Writes this seat's end-of-game legacy note (Game/Story/Legacy/legacy-<colour>.md) for this seat's own colour, giving a future game's bot of the same colour a narrative thread to build from — and resolves this seat's own departing Codex cast, either closing them out (Died year, past tense, moved to codex/characters/historical/) or, if the elapsed time between games leaves them a plausible age, aging them into a living NPC instead. Use once the game has ended and the Chronicle phase has reshaped the board, when the user asks to "leave a legacy", "write the legacy file", "close out this character for next time", or similar. Run once per AI-controlled colour, in that colour's own chat.
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
2. Reread `Game/Story/oath-chronicle.md` and this seat's
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
   For each one still `Active` in `codex/characters/`, check plausible
   age first: their age (or a reasonable estimate) at this game's end,
   plus step 1's elapsed years. Two outcomes, per Bot-Rules, "Codex —
   using it in play," "Current vs. historical":
   - **Implausibly old, or a specific reason they wouldn't have
     survived the years between** — close out. Decide, briefly, how the
     elapsed years went for them, set Status to Deceased with a Died
     year (per Bot-Rules, "Dating a Codex entry"), add a sentence or two
     on what's remembered of them, and convert Description and History
     to past tense throughout.
   - **Still a plausible age, or long-lived/effectively immortal
     regardless of age** — don't close them out. They stay `Active`,
     present tense, but no longer this seat's own Player Character:
     update Description and History to reflect the years passed (older,
     changed circumstances, whatever the elapsed time plausibly did to
     them) and note in Status that they're now an NPC available to a
     new character or anyone else, not this colour's own active seat
     anymore. This is the default whenever the arithmetic supports it,
     not a rare exception — don't reach for Deceased out of habit just
     because that's the usual shape of a legacy pass.
8. Move each entry closed out (the first outcome in step 7) into
   `codex/characters/historical/` (per Bot-Rules, "Codex — using it in
   play," "Current vs. historical") — the folder move and the narrative
   closure happen in the same pass, not as separate steps. A character
   kept under either exception in step 7 — persistence, or simply still
   plausibly alive — stays in `characters/`.
9. Also check for any leaked game terms in the codex files and fix them: the codex is written by a historian who doesn't know what a Round, an NPC, or a post-game is.
10. Leftover cast not clearly owned by this seat — companions or NPCs
    this character interacted with but didn't personify as its own
    adviser — aren't this skill's job to close out. Flag them in this
    skill's own Response for whichever human player is doing the wider
    sweep across all seats, rather than guessing at cast that isn't this
    colour's own.

## Response

Print the legacy entry just written (step 6), and a short list from
step 7-8 of what happened to each Codex entry checked — which were
closed out and moved to `historical/`, and which were kept `Active` as
living NPCs instead, with why — plus any leftover cast flagged in step
9 for a wider sweep — so the human can confirm all of it before the
next game starts.

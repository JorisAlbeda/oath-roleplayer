---
name: oath-leave-legacy
description: Writes this seat's end-of-game legacy note (Game/Story/Legacy/legacy-<colour>.md) for this seat's own colour, giving a future game's bot of the same colour a narrative thread to build from. Use once the game has ended and the Chronicle phase has reshaped the board, when the user asks to "leave a legacy", "write the legacy file", "close out this character for next time", or similar. Run once per AI-controlled colour, in that colour's own chat.
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

1. Reread `Game/Story/oath-chronicle.md`'s final beats and this seat's
   own `Game/Story/Diaries/oath-diary-<seat>.md` in full,
   especially anything involving this character's most significant
   bond, rivalry, or unresolved thread with another character — and
   anything in the Codex (an adviser, denizen, or commander this
   character personified) that mattered enough to be worth carrying
   forward.
2. Look at every photo in `Board Photographs/Endgame-Before` and every
   photo in `Board Photographs/Endgame-After`, if they exist (if not, skip this step). Note what's visibly
   changed, especially near this character's own ground, if anything —
   don't interpret or state mechanical game state from either folder,
   just the physical look of things (a banner moved, a site's tokens
   cleared, and so on).
3. Write an in-world fragment left behind — a family record, an
   heirloom, a debt, a reputation, or a rumor — grounded in at least one
   physical detail actually seen changing between the two folders, if
   this character's own ground shows one.
4. Keep it under 200 words, written as something a future character
   would actually possess or have heard, not a plot summary. Follow the
   specificity standard in `Oath-Cowork-Bot-Rules.md`, "Roleplayer —
   Guidelines," as always.
5. `Game/Story/Legacy/legacy-<colour>.md` holds only this colour's most
   recent legacy, not a running family history. If the file already
   exists from an earlier game, read it fresh immediately before
   writing (never rely on an earlier read this conversation), then
   replace its contents entirely with this game's fragment, headed
   `## <Character Name>` — the previous entry doesn't carry forward
   once this one's written. If the file doesn't exist yet, create it
   with this as the only entry. This skill doesn't create or update a
   portrait image for the colour — see `oath-setup-character`, which
   only reads one if it already exists.

## Response

Print the entry just written. There's nothing else in the file to spare
the reader from anymore — this replaces whatever was there before.

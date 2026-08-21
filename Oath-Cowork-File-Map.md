# Oath Roleplayer - World Codex: File Map

_Three Cowork chats, one per AI seat — not six. Each seat's own bot
reads all shared documents plus its own private ones; it never reads
another seat's private documents. The Human seat has no chat of its
own and no private documents._

All live game files sit in a `Game/` subfolder of this Oath Roleplayer
folder. `oath-game-setup` creates that subfolder and its structure once,
at the start of a new game — every other skill assumes it already
exists.

`Game/` splits into three subfolders — Mechanics, Setup, and Story:

- **Mechanics** — Board state, Player state, Logic log, Strategy (one
  per AI seat, written and overwritten by `oath-inspect-board` — not
  append-only, holds only this seat's current thinking).
- **Setup** — World Briefing.
- **Story** — Chronicle, Characters, plus four further subfolders:
  Conversation logs, Messengers, Diaries, and Legacy.

**The Codex is not part of `Game/` at all, and it is not part of this
project folder either.** It lives at a single fixed location, outside
every playtest folder: `Catalogue/codex/`, a sibling of the `Oath/`
folder's various playtest projects (this project's own folder — "Playtest
6 - The Second Woodland Empire" or whichever one is current — sits
alongside it, not above or below it). It holds five subfolders —
`buildings/`, `characters/` (with its own `historical/` subfolder for
retired characters), `events/`, `locations/`, `relics/` — plus a
`timeline.md` and a `manifest.json` at its own top level. One Catalogue
serves every playtest that's ever been run, which is the entire point
of it: a character, location, or relic from three playtests ago is
still there to be read and built on.

**No skill ever creates a Codex folder, anywhere, under any
circumstances — not at Setup, not lazily on first use, not as a
fallback when one "isn't there yet."** The Catalogue already exists
and is provided by the human; the only way to see it is a folder-access
problem, never an existence problem. If a bot can list `Game/` but the
Catalogue's `codex/` folder doesn't resolve, that means this session
hasn't been granted access to it yet — the fix is to ask the human to
connect or grant access to `Catalogue/codex/` at its existing path, the
same way any other connected folder gets granted, never to create a
same-named folder somewhere convenient and start writing to that
instead. (This is a corrected mistake, not a hypothetical: an earlier
session did exactly that during Playtest 6, inventing a fresh top-level
`Codex/` folder inside the playtest project and populating it there.
The stray folder was moved out and its two entries relocated into the
real Catalogue; this paragraph exists so it doesn't happen a second
time.)

## Shared documents (all seats read and append to these)

- `Game/Mechanics/oath-board-state.md` — Board state: Round, Visions
  Drawn, Oath, Current Player Turn, World Deck Search cost, Favor Banks
  (an exact count for each of the six suits — Discord, Hearth, Beast,
  Nomad, Order, Arcane), and the Map. Filled in full from board
  photographs once, during `oath-game-setup` — the only time the whole
  board is ever photographed; kept current afterward from the Logic log
  alone. Each Region also carries its own Discard Pile count (how many
  cards currently sit on it), alongside its Travel and Search Discard
  Pile cost. The Map holds one entry per Region, one sub-entry per Site
  within it:
  - Name
  - Ability
  - Ruled by
  - Number of warbands
  - Relic cost
  - Content (if relevant)
  - Number of defence dice
  - Relics (Name and Description once peeked at, otherwise "unknown")
  - Denizens (present at the site until Mustered or otherwise taken by
    a seat), each with:
    - Name
    - Suit
    - Ability cost
    - Ability
- `Game/Mechanics/oath-player-state.md` — Player state: one row per
  colour (Role, Controlled by, Location, Region, Number of Supplies,
  Number of Secrets, Number of Favors, Banners, Revealed Vision — Name
  and Goal, or "none"), plus Warbands in reserve — a real count for an
  Exile or the Chancellor (the Chancellor's is the Empire's one shared
  bank, also read by every Citizen row), or a one-line note for a
  Citizen that they share the Chancellor's reserve instead of holding
  one of their own (see Bot-Rules, "Warband reserve and the Supply
  refresh table"), each with its own Advisers (Name, Source card,
  Ability, Ability cost, Status) — the mechanical half of a personified
  adviser/denizen/commander; the narrative half is the matching Codex
  `characters/` entry, same Name. A facedown Vision kept as an adviser
  gets a placeholder row instead — Name "Vision (unrevealed)" — never
  its real identity, per Bot-Rules, "Codex — using it in play," "A
  facedown Vision is a narrower case than a facedown denizen"
- `Game/Story/oath-characters.md` — Characters (all seats' public
  entries), including a lighter Acquaintances field alongside Bonds
  (name, one-line relationship, what they might know or want),
  established at character creation per Bot-Rules, "Character creation
  — background flavor and starting social circle." Motivation isn't its
  own field — it lives inside Personality description, alongside Flaw
  — and may get a short appended note later if this seat's own Role
  genuinely changes or a Vision is revealed, per the same Bot-Rules
  section
- `Game/Mechanics/oath-logic-log.md` — Logic log
- `Game/Story/oath-chronicle.md` — Chronicle, plus a `## Live threads`
  header at the top (2-3 narrative-only tensions, overwritten as they
  resolve or emerge) — the one part of this file that isn't append-only,
  per Bot-Rules "Live threads — narrative-only tension tracking"
- `Game/Story/Conversation logs/oath-conversation-<nameA>-<nameB>-R<round>-<n>.md`
  — one file per Converse dialogue, created on first use, named after
  the two characters and the round it started in (e.g.
  `oath-conversation-dorcas-lyn-R2-1.md` for the first conversation
  between them in Round 2)
- `Catalogue/codex/` — in-world detail on buildings, characters, events,
  locations, and relics, one file per entry in the matching subfolder
  (`buildings/`, `characters/`, `events/`, `locations/`, `relics/`),
  each an H1 title followed by `##` sections — Description, History,
  Location, in that order (see any existing entry, e.g.
  `characters/tavin-aldren.md` or `relics/grand-scepter.md`, for the
  exact shape) — not a flat Title/Description/History/Location bullet
  list. `characters/` entries carry a fifth `## Voice` section, per
  Bot-Rules "Voice — staying in character," and may also carry an
  optional `## Status` section (e.g. "Active — Born Year 512");
  `locations/` entries may optionally carry Regional voice notes, added
  the first time a scene actually happens there, and may also optionally
  carry a Garrison field (a name, a leader as a minor `characters/` NPC,
  its own character) for that site's own ruling force, added or updated
  per Bot-Rules, "Warbands — personifying the garrison." This is not a
  subfolder of `Game/`, or of this project folder at all — see the
  note near the top of this document on where the Codex actually lives
  and why no skill ever creates it. Mostly inherited from
  previous games, extended during this one — read per Bot-Rules "Codex —
  using it in play," appended to (new History) or added to (new
  entries) the same way
- `Catalogue/codex/timeline.md` — long-form world history across games,
  dated by era of the Old Oak, occasionally with editorial commentary.
  Human-maintained and read-only for every seat's bot — no skill writes
  to it. Read once, by `oath-setup-character`, to place a new character
  in the world's current era.

## Private, per-seat documents (this seat's bot only)

- `Game/Story/Diaries/oath-diary-<seat>.md` — this seat's
  Diary
- `Game/Story/Messengers/oath-messengers-<seat>.md` — this seat's
  Messengers
- `Game/Mechanics/strategy-<colour>.md` — this seat's current strategy,
  written and overwritten by `oath-inspect-board`; not created by
  `oath-game-setup` — the first `oath-inspect-board` run creates it
  lazily
- `Game/Setup/oath-world-briefing-<seat>.md` — this seat's World
  Briefing, written once by Game Setup, read by this seat's own Setup
- `Game/Story/Legacy/legacy-<colour>.md` — this colour's Legacy, keyed
  by **colour** rather than seat/Name since it outlives any one
  character and needs to be findable before this game's own
  `oath-setup-character` decides the next Name. Not prefixed `oath-`, unlike
  everything else here. Each new game's
  `oath-leave-legacy` wipes the page and starts anew. A portrait image may sit
  alongside it in the same folder, named after the colour (e.g.
  `Purple.png`) — a visual reference for whoever held that colour
  previously, checked by the next game's `oath-setup-character` but
  never created or modified by anything in this Skills set.

No Strategy or World Briefing file is created for the Human seat — the
human has no bot reading or writing on their behalf. A Messengers file
is still created for the Human seat, since their character can receive
messages even without a bot; a Diary file is not, since there's no bot
of its own to write turn-by-turn diary entries.

## Reference material (read-only, shared)

Rules, Site Reference, and action summary in this project's connected
folder. Never written to.

## Append-only convention

Every shared document above is append-only, and is edited by other
seats' bots as well as your own. Before appending to any of them, read
it fresh, immediately beforehand — never rely on an earlier read from
this conversation, even one from a few turns ago. This was confirmed as
a real failure mode during Playtest 2 and applies here with the same
force. Append at the very end of the file; never insert earlier in it.

Converse dialogue files are the one shared document that isn't
appended-to by every seat generally — only by the two participants in
that specific conversation — but the same fresh-read-before-append
discipline applies, since both sides write to the same file. Legacy is
the one file in this list that grows _across games_, not just within
one — the same rule still applies, just on a longer timescale: a new
game's entry never overwrites or edits a previous generation's.

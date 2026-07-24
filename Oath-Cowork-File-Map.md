# Oath Experiment 6 - World Codex: File Map

_Three Cowork chats, one per AI seat — not six. Each seat's own bot
reads all shared documents plus its own private ones; it never reads
another seat's private documents. The Human seat has no chat of its
own and no private documents._

All live game files sit in a `Game/` subfolder of this Experiment 6
folder. `oath-game-setup` creates that subfolder and its structure once,
at the start of a new game — every other skill assumes it already
exists.

`Game/` splits into three subfolders — Mechanics, Setup, and Story:

- **Mechanics** — Board state, Logic log, Strategy (one per AI seat,
  written and overwritten by `oath-inspect-board` — not append-only,
  holds only this seat's current thinking).
- **Setup** — World Briefing.
- **Story** — Chronicle, Characters, plus five further subfolders:
  Conversation logs, Messengers, Diaries, Codex, and Legacy.

## Shared documents (all seats read and append to these)

- `Game/Mechanics/oath-board-state.md` — Board state, including each
  seat's Advisers (Name, Source card, Ability, Ability cost, Status) —
  the mechanical half of a personified adviser/denizen/commander; the
  narrative half is the matching Codex `characters/` entry, same Name
- `Game/Story/oath-characters.md` — Characters (all seats' public entries)
- `Game/Mechanics/oath-logic-log.md` — Logic log
- `Game/Story/oath-chronicle.md` — Chronicle
- `Game/Story/Conversation logs/oath-conversation-<nameA>-<nameB>-R<round>-<n>.md`
  — one file per Converse dialogue, created on first use, named after
  the two characters and the round it started in (e.g.
  `oath-conversation-dorcas-lyn-R2-1.md` for the first conversation
  between them in Round 2)
- `Game/Story/Codex` — in-world detail on buildings, characters, events,
  locations, and relics, one file per entry in the matching subfolder
  (`buildings/`, `characters/`, `events/`, `locations/`, `relics/`),
  each following a Title/Description/History/Location structure. Mostly
  inherited from the previous game, extended during this one — read per
  Bot-Rules "Codex — using it in play," appended to (new History) or
  added to (new entries) the same way
- `Game/Story/Codex/timeline.md` — long-form world history across games,
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
  everything else here, matching Experiment 3's own Legacy naming.
  Append-only _across games_, not just within one — each new game's
  `oath-leave-legacy` adds one more `## <Character Name>` entry at the
  end rather than starting a new file. A portrait image may sit
  alongside it in the same folder, named after the colour (e.g.
  `Purple.png`) — a visual reference for whoever held that colour
  previously, checked by the next game's `oath-setup-character` but
  never created or modified by anything in this Skills set.

No Diary, Messengers, Strategy, or World Briefing file is
created for the Human seat — the human has no bot reading or writing on
their behalf.

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

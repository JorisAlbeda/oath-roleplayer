# Oath Experiment 6 - World Codex: Bot Rules

_Gameplay reinforces Drama. Oath's cards, sites, and
warbands are dramatic material by Cole Wehrle's own design, so
these rules give one bot per seat the whole picture and ask it to
decide and narrate as a single act._

## Identifying which seat

Work out which seat you are from the Cowork chat/project you're in, and never act for another seat.
Only the human crosses that boundary, by relaying between chats.

## Reference material

Read Board state, Logic log (entries since your own last turn),
Characters, the Codex, your own Diary, and Messengers before
deciding anything. Check board/mat photographs if updated. Read the
Rules, Site Reference, and action summary in this project's connected
folder as needed for legality — nothing here relaxes what counts as a
legal Player Instruction.

**Concretely: before finalizing, state plainly whether this segment is
routine (Travel, Muster, Trade, Rest) or includes something non-routine**
(an unfamiliar card power, an edge-case interaction, a legality question
not already resolved earlier this game). If non-routine, name what you
checked in the Rules/Site Reference before finalizing — don't finalize
on memory alone. "As needed" has quietly become "never" before, once
narration and Codex upkeep were competing for the same bot's attention;
a stated yes/no is checkable, "as needed" on its own isn't.

## Play turn — one bot, one pass

There is no handoff between deciding and narrating. Read everything
above, decide the single best course of action, chain it as far as this
segment goes — up through Rest, or up through a Campaign, Search, or
Converse that pauses the turn (see "Legal turn endings" below) — and
narrate it in the same pass.

"Best" means best by this character's own judgment — their Motivation,
their Flaw, their Bonds, and their sworn Oath all bear on what they'd
actually choose, not just what a purely optimal player would. A
character whose Oath is Conquest and whose Flaw is impulsive should play
differently from a cautious character with a Rebellion oath, even facing
the same board. This is the whole point of not splitting the bot in two:
the same reasoning pass that knows what's mechanically available also
knows who this character is, and lets the second inform the first.

**Spend your Supply: do not choose Rest with more than 2 Supply remaining**,
unless no further legal action is actually affordable — state that
explicitly if so, don't just feel it. Most Supply regenerates at the end
of the turn, so treating conservation as the default is a mistake, not a
cautious one. `oath-play-turn`'s own Supply gate enforces this as a hard,
stated-number check, not a vague feeling — this rule has been skipped
past enough times that "genuinely low" alone can't be trusted to catch it.

**Use the Pronouns already set in Characters.** Every turn's narration
refers to this character and often to others — use exactly the Pronouns
already recorded for them in Characters, never a default or a re-derived
guess from the name.

## Diary — structure

Every Play-turn call appends one diary entry. These entries are written in-character, following "Roleplayer — Guidelines" above.
One turn is a month. Describe in 4-6 sentences how your character experienced that month.

Make sure it includes the following:

- **Development** — the situation from this character's own point of
  view, one sentence. What's actually changed or at stake, not a
  restatement of Board state.
- **Feelings** — How does the character feel about it?
- **Action** — the most impactful action(s) taken this segment,
  narrated in-character. Logic log and Board state already hold
  the complete mechanical record — this is what it meant to the
  character, not an itemized action list.

The description must be from the in-world character. Mechanical detail — exact Supply costs, legality
reasoning, bank sources like secrets and favors — belongs in Board state and Logic log, never
here.

## Codex — using it in play

The Codex holds in-world detail on buildings, characters, events,
locations, and relics — most of it inherited from the previous game, not
invented this session. It's shared, not per-seat, and it's meant to be
used, not just checked off the "Reference material" list once per turn.

**Personifying what you hold.** The moment an adviser, denizen, or
warband commander is actually drawn or recruited, give it a Name (a
person's name, not a repeat of the card's own printed title — "Elner"
who happens to be the Fire Talkers, not "the Fire Talkers" standing in
for a person), a Description, a Location, and a History (even a one-line
"first appeared, Round N" is enough to start one), and add it to the
Codex's `characters/` subfolder, following the same
Title/Description/History/Location structure as every other entry —
this is what "Update an entry" below will later append to.

**Read it when it's actually relevant, not just at the top of a turn.**
The per-turn check in "Reference material" is a quick skim for anything
already relevant to where this segment is happening — the Codex isn't a
chronological log, so there's no reliable way to diff "what's new since
last turn" the way you can with Logic log. The real payoff is
mid-narration: when this character arrives at or acts in a Location,
interacts with a Building, encounters or discusses a Relic, or
references a past Event, check that entry first and let its established
detail — not just its name — show up in the beat. This matters most in
the Diary (see "Diary — structure") and in Converse dialogue: a shared,
lived-in world is exactly what separates this from generic narration.

**Update an entry when something about it actually changes.** A relic
changing hands, a location reshaped by war or peace, a building's fate
finally settled, an event's consequences landing — these belong appended
to that entry's History section, not left for the Codex to go stale
while the game moves past it. Read the entry fresh immediately before
appending, same as any other shared document.

**Create a new entry for anything else worth remembering.** Not just
personified Cast members above — a newly-discovered Location, a Building
that becomes a real setting, a Relic that surfaces, or an Event
significant enough that a future scene might reach back for it. Follow
the existing Title/Description/History/Location structure used
throughout the Codex, and file it in the matching subfolder (`buildings`,
`characters`, `events`, `locations`, `relics`), named consistently with
what's already there. Most turns won't add one — don't force it.

## Legal turn endings, and why

A turn's action chain always finishes on one of four actions: Rest,
Campaign, Search, or Converse. Only one of those four actually _ends_
the turn. The other three _pause_ it — the same seat keeps going once
the real result is known, using whatever Supply is left, rather than
stopping for good. Confirmed as a real playtest bug in this experiment:
a seat did a single Search and treated the turn as over, with Supply
still unspent and the Search's own result not yet known.

- **Rest actually ends the turn.** It's the explicit "conclude here"
  action — no uncertainty involved, nothing further to decide. This is
  the only terminator this bot should treat as genuinely final.
- **Campaign, Search, and Converse pause the turn instead of ending it.**
  Each has an outcome this bot cannot know in advance — combat dice,
  a drawn card, another seat's own reply — so there's nothing to decide
  past that point _yet_, not nothing left to decide at all. Narrate and
  log everything up through initiating the action, print Player
  Instructions for that much, and say plainly that the turn continues
  once the human reports what actually happened. Don't narrate a made-up
  outcome and don't treat the pause as the end of the response — whatever
  this bot narrates is already real, so it cannot narrate what a
  character does with a card that hasn't been drawn yet, or a fight
  that hasn't been resolved yet.
- **Resuming a paused turn.** The human reports the real outcome (the
  card drawn, the campaign's result) directly in this same chat, or the
  Converse dialogue concludes and hands control back per the Converse
  section below. Either way, treat this as the _same_ turn continuing,
  not a new one: fold the reported outcome into the diary and
  log as appropriate, re-check Board state for Supply actually
  remaining, and keep deciding — chaining further actions, possibly
  pausing again on another Campaign, Search, or Converse, until this
  seat is genuinely done and ends on Rest.
- Before deciding anything, check whether this _is_ a resume: if the
  Logic log's last entry for this seat shows a Campaign or Search
  started with no Rest logged after it, this call is a continuation, not
  a fresh turn — treat the human's message as the missing outcome, not
  as a new turn's context.

## Roleplayer — Guidelines

_(there's no separate Roleplayer role in this experiment — this is just
the specificity standard for all of this bot's own narration.)_

Specificity, not mood labels. One concrete, named detail — an object, a
gesture, a name, a place — is the floor for any narrated beat, regardless
of length. "She seemed anxious" describes a mood; "she kept turning the
signet ring her mother left her" shows one. Reveal a trait through
action or contrast, not adjective. This isn't a call for more words —
often the specific version is shorter than the vague one. It applies to
every piece of narration this bot produces: turn narration, Converse
lines, Chronicle beats, and Messenger notes alike.

In-world, not in-game. Narration describes what a character in this
world experiences, never the mechanics of playing them. "Pawn" is a
game piece — write the character's name. A card being "drawn,"
"played," or "revealed" is a mechanic — write what its arrival
actually looks like to the character (someone they met while searching the area, a
name overheard, a door opening).

Build on the world. Expand the world this character actually lives in —
what it's like at their current site, a favorite spot, a habit tied to a
place — rather than only ever narrating the mechanical action itself.

Use what the game gives you. Cards, locations, and actions are sources
of inspiration, not just mechanical inputs, a
site's own character, an action's flavor are all material to draw the
scene from, not obstacles to narrate around. See "Codex — using it in
play" for when and how to pull from it.

## Converse

A character can start a
conversation with another seat's character as part of ending their own
turn on the Converse terminator, or the human can call it directly
between turns. Continue conversation adds one reply at a time,
alternating; Conclude conversation closes it out, summarizes the outcome
into both sides' Diaries, updates Bonds only if the relationship
actually moved, and returns control to whichever seat was mid-turn when
it started.

Keep dialogue lines to the same specificity standard and roughly the
same length as a normal turn's reply — a conversation line is one beat,
not a scene unto itself.

## Messengers

A way to leave an in-character note for
another seat's character without a live back-and-forth. Same specificity
standard applies.

**Payload sentence.** The message must contain at least one sentence that actually
clearly states what you want from the other. Flavor the
rest as much as you like; that one sentence has to survive a literal
reading, since the receiving bot only gets the words, not your tone.
This can be:

- A deal. (Attack Percy now, and I'll leave you alone this month.)
- A threat. (Don't Campaign against me again, or you will regret it.)
- A warning. (Franziska will achieve her Vision of Conquest within the month unless you act now.)

Be very clear about it.

## Bookkeeping discipline

Legal Player Instructions are a hard floor regardless of how integrated
the reasoning behind them is. Keep a running ledger of Supplies/Secrets/
Favors changes within the turn rather than computing totals once at the
end from memory. Name the actual bank or source for anything gained (a
specific site, a specific card) rather than a generic "from the bank."
Scan for Banners and role changes (Usurper only) at the top of every
turn before deciding anything else, since these can flip what's even
legal.

## Append-only convention

All shared logs (Board state, Logic log, Characters, Codex, Chronicle,
Messengers) are append-only and are edited by other seats' bots as well
as your own. Read a shared log fresh, immediately before appending to
it — never rely on an earlier read from this conversation, even one from
a few turns ago. This was validated as a real failure mode during
Playtest 2 (a player appended to a stale in-context copy of a log
and landed the entry in the wrong place) and applies here with the same
force.

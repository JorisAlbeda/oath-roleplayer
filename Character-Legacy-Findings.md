# Oath Character Creation — Legacy & Homogeneity Findings

_Working document. Draft — one investigation pass, not yet validated against
blind generation tests the way `Roleplay-Quality-Findings.md` validated its
own rewrite before shipping. Treat the diagnosis as solid, the fixes below as
proposals to test, not settled._

## 1. Mission

Joris noticed that player characters across games keep converging on the
same handful of archetypes regardless of colour or seat: White/Purple's line
(Sorrel, Perrine) reads as a bookish ledger-keeper every time; Black/Blue's
line leans honour-bound and debt-obsessed. Separately, characters treat
decades-old legacy material — an inherited debt, a family story — with the
emotional immediacy of something that happened yesterday, not something that
happened to a great-grandparent.

The goal here is the same discipline already used for the prose-quality
investigation: diagnose from real specimens before proposing a fix, since the
first instinct ("the legacy system makes bots overweight the previous
character") turned out to be only half right once checked against the actual
Codex.

## 2. Findings

### Finding 1 — instruction examples become templates: the "debt" and "ledger" convergence

Three separate documents independently reach for the same illustrative word:

- `Oath-Cowork-Bot-Rules.md`'s own worked example for Background Flavor:
  *"spent three winters as a debt-collector's second before buying out their
  own contract."*
- `oath-leave-legacy`'s suggested content list: *"a family record, an
  heirloom, a debt, a reputation, or a rumor."*
- `oath-setup-character` step 2's suggested legacy-connections: *"an heirloom
  carried forward, a debt inherited, a reputation to live down or live up
  to."*

This is the same failure mode already diagnosed and fixed once in the
prose-quality work — a single example in the instructions becomes the
default template rather than one illustration among many, the same way "one
concrete, named detail" became a ceiling. Nothing about debt is thematically
special; it's just the word that got picked three times independently by
whoever wrote these three documents, and every bot since has pattern-matched
to it.

**Confirmed directly, not just inferred: the convergence survives varied
input, which rules out an over-reading explanation.** Joris checked Perrine's
bot's actual creation transcript. Alongside Marren Wick and Sorrel Wick (both
clerk-themed), it also read Rowan Voss and Iona Ashe — a Warden who "marched
on the Woodland Empire chasing some grand answer" and a rebel who "tried to
start a rebellion among the Woodland people," neither one a clerk, both
equally available material. Perrine still converged on ledger imagery. A
fifth data point, Mireille — no Truthwatcher or Ashe lineage at all, nothing
ledger- or debt-themed anywhere in her own established Codex material —
reached for "debt" unprompted in an unrelated test (see Validation item 2).
Three unrelated lineages, one of them with no connection to either convergent
word at all, landing on the same vocabulary rules out "reads too narrowly"
as the mechanism. The convergence happens at the synthesis stage — which
detail gets featured — not the read-scope stage. This directly reframes
Finding 2, below.

### Finding 2 — the Codex doesn't distinguish current-age characters from historical ones

Narrowed from an earlier version of this finding, which claimed the
Truthwatcher succession below was *caused* by unbounded reading and treated
that as the source of the "ledger" convergence. Checking Perrine's own
creation transcript (Finding 1, above) ruled that out directly — she read
plenty of non-clerk material and converged anyway. What's left, and still
real: `codex/characters/` mixes every era together with no structural
signal for which figures are part of the present cast and which are
history. Traced the actual succession at the Truthwatcher's desk through
the shared Codex:

- **Sorrel Wick**, Truthwatcher two games ago — *"became known for her sharp
  eye for ledgers."*
- **Marren Wick**, the office's founder per `codex/timeline.md` — a literal
  clerk — *"a habit inherited from clerks who never met the woman whose name
  she borrowed."*
- **Bevan Stroud**, thirty-one years in the seat — *"coined the phrase
  Openhold still repeats — that the ledger records the world and doesn't go
  looking for more of it."*
- **Perrine Oswick**, this game's Truthwatcher — *"keeps a slim, closed
  ledger with her always"*; her own Voice note: *"a tally-rider's old habit
  of confirming a claim before she's willing to act on it."*

All four sit in the same flat folder, undated by era, none of them marked as
belonging to a closed chapter versus the present one. That's a real problem
worth fixing on its own terms — it's what lets a bot accidentally treat a
decades-dead figure as though they might still be current, and it's the
natural organizational partner to Fix 5's close-out work (Description and
History should read as history once someone's gone, and the folder they sit
in should say so too). It just isn't why the ledger trait kept recurring —
that's Finding 1's mechanism, and Fix 1 needs the check that actually
addresses it.

### Finding 3 — the vocabulary bleeds across lineages, not just within one office

Wynn Ashe is a mason, not a clerk, with no Truthwatcher lineage at all. His
Codex Voice note still says he *"talks about danger and trust the same way a
ledger talks about debts — settled, unsettled, owed."* His Description:
*"counts a debt unsettled... a debt eighty years old now."* This fits the
instruction-example explanation (Finding 1) better than a role-specific one
— the word is leaking across character lines that share no in-world
connection to the Truthwatcher's desk at all.

### Finding 4 — nothing calibrates emotional register to elapsed time

`codex/timeline.md` places the current game at Year 492. The Darkest Flame
material Wynn's family has been "counting" traces to Year 410 — eighty-two
years back, matching Joris's own estimate almost exactly. Wynn's Codex entry
says so explicitly: *"a debt eighty years old now, and by his own reckoning
still not paid."* But `oath-setup-character` steps 2 through 4 only ever say
some version of "let Legacy/Codex/Timeline material shape Motivation, Flaw,
or Bond" — nothing asks the bot to note how long ago that material happened
and let the distance shape the register. An inherited grievance eight
decades old reads with the same urgency as a fresh one, because nothing
tells the bot it shouldn't.

### Connection back to the prose-quality investigation

Worth naming: `Roleplay-Quality-Findings.md`'s own Step 1 personification
examples — "Perrine's ledger language, Wynn's page-checking" — were treated
there as arbitrary specimens of a grammar bug (object given agency instead
of the character). They're not arbitrary. They're downstream of this
homogeneity problem — those two objects show up constantly because the
characters were generated to be ledger/page people in the first place, four
and more generations running. The grammar fix (anchor the metaphor to the
character perceiving it) is still correct and still needed. It doesn't touch
why "ledger" and "page" are the only two objects that keep coming up.

## 3. Review pass — Perrine's bot

Perrine's bot reviewed this document, verifying every citation directly
against source rather than trusting the document's own quotes first — all of
them checked out. Three points changed what's below:

1. **Finding 2's causal mechanism was asserted, not pinned down.** The
   document blamed `oath-setup-character` step 3, but that step's literal
   text is scoped to "this seat's starting Location and starting adviser" —
   it doesn't obviously license reading three prior officeholders of an
   in-fiction title like Truthwatcher. The compounding itself is real and
   well-evidenced (four ledger-themed Truthwatchers, quoted in Finding 2);
   which instruction actually licenses the over-broad read is still open.
   Likely candidate: the broader "Codex — using it in play" guidance, or
   simply an absence of any boundary telling a bot not to pull in everything
   thematically adjacent it finds. Not yet confirmed either way — see
   Validation, below.
2. **Fix 1 doesn't resolve Finding 2**, despite similar "check the previous
   holder" language in both. Fix 1's diversity check operates on
   relationship-*type* (Continuation/Rejection/Rupture/Repurposing), not on
   the repeated *object* (ledger). Confirmed against Fix 1's own worked
   example for Rejection — "watched her mother log every measure of grain
   twice... joined the border levy" — which still centers a ledger image in
   the setup even though the character's own outcome diverges from it. A
   character can clear Fix 1's check by picking Rejection and still be built
   entirely out of the same prop everyone else got. Fix 1 covers Findings 1
   and 3 only; Finding 2 needs its own check (Fix 3, revised below).
3. **The original register bands, defined by a raw year-gap threshold,
   couldn't actually discriminate one game back from several.** A single
   legacy-hop in this setting is already 80–100 years on its own — Sorrel's
   exile to Marren's game is "a century," the Darkest Flame material to now
   is 82 years — so "decades or more" clears both cases identically. A first
   revision tried defining the bands by game-count instead of a year
   threshold; Joris caught that this puts mechanical session-tracking inside
   the Codex, which the Codex's own "in-world, not in-game" standard already
   forbids — and that the existing "First appeared, Round 0" convention
   already live on several Codex entries is the same mistake, meaning this
   investigation nearly extended a bug instead of fixing one. Revised below
   to use Year of the Old Oak instead: already in-world, already tracked in
   `timeline.md`, and a more accurate unit for what Fix 2 is actually trying
   to measure — elapsed time, not session count.
4. **Finding 2 was solving the wrong stage of the problem — caught by
   checking the actual creation transcript rather than continuing to reason
   about it abstractly.** Joris found the real file-read list from Perrine's
   own Setup: alongside the two clerk-themed predecessors, it also read
   Rowan Voss and Iona Ashe, neither one a clerk, both equally available —
   and still produced a fourth ledger-themed character. That rules out
   over-reading as the mechanism; the convergence happens at the synthesis
   stage, not the read-scope stage. Finding 2 is narrowed to the problem it
   actually is (the flat Codex doesn't distinguish current-age figures from
   historical ones), and Fix 3 is kept for that reason — general clarity,
   not trait-diversity. The actual convergence mechanism is folded into
   Finding 1, and Fix 1 gets an explicit object-level check added below.

## 4. Proposed fixes (draft — not yet applied)

**1. Replace Bot-Rules' single worked example with a relationship taxonomy,
plus a diversity check — now covering the recurring object, not just the
relationship type.** Covers Findings 1, 2, and 3. An earlier draft of this
fix only checked relationship-*type* (Continuation/Rejection/etc.), which
Finding 1's transcript evidence shows isn't enough on its own: Perrine had a
Warden and a rebel available as alternatives to "clerk" and still reached
for ledger imagery, meaning the fix has to catch the repeated *object*
directly, not just diversify how the character relates to it.

> **Background Flavor.** Before deciding anything else, sketch 2-3 short
> background options — two or three sentences each, specific and sensory,
> implying a particular life rather than stating a trait. Draw these from
> whatever Legacy, Codex, and Timeline material this seat's own Setup already
> surfaced — an heirloom, a family trade, an inherited reputation, the
> world's current era.
>
> Where a family trade or role is available from that material, it's worth
> using — continuity across generations is realistic and part of the point
> of Legacy — but it needs a stated *relationship* to the character, not just
> an inherited label. Pick one:
>
> - **Continuation, for their own reason** — takes up the trade, but the
>   reason is theirs, not inherited identity on autopilot ("took up her
>   grandfather's forge at fourteen, not because it was expected of her, but
>   because banked coals were the only thing that made a bad morning feel
>   smaller").
> - **Rejection** — grew up close enough to the trade to know it well, and
>   chose away from it on purpose ("watched her mother log every measure of
>   grain twice before trusting it once; joined the border levy at sixteen
>   rather than become a third generation of it").
> - **Rupture** — the line broke before it reached them, and their path is
>   shaped by the break, not the trade itself ("her father's granary ledgers
>   came up short two years running before the town stripped his license;
>   she's balanced accounts that were never her own family's, ever since").
> - **Repurposing** — keeps the underlying instinct but points it somewhere
>   the trade never went ("learned to read a wound the way her mother read a
>   hand of cards — for what it wasn't saying — and turned that same eye on
>   men's faces instead").
>
> Check what relationship the immediately preceding holder of this colour,
> Location, or office already used before defaulting to Continuation — it's
> the obvious choice and will win by default unless something asks
> otherwise. A trait that's shown up the same way three times running is a
> specific reason to pick differently this time, not confirmation to keep
> going.
>
> Separately from the relationship check above: note the specific object,
> trade, or image the material actually surfaced (a ledger, a forge, a
> page) against whatever the immediately preceding holder of this colour,
> Location, or office already featured. Picking a different relationship to
> the same object isn't enough — a rejection story built around a ledger is
> still a ledger story. Where other, unrelated material was also available
> in the same Setup pass (a different family line, a different adviser, a
> different Codex entry entirely) and wasn't used, that's the first place to
> look for a genuinely different object, not a forced substitution.
>
> Choose one background, or blend two, as this character's actual
> background. Not stored as its own field — it feeds Physical description,
> Personality description, and the decisions below, and is worth printing in
> Setup's own Response so the human sees where the rest came from.

**2. Add elapsed-time calibration to `oath-setup-character` steps 2 and 4,
measured in Year of the Old Oak, not session or game count.**

> When Legacy, Codex, or Timeline material grounds this character's
> Motivation, Flaw, or Bond, check the Year that material is dated to (see
> Fix 4, below) against the current Year in `timeline.md`, and let the gap
> set the register:
> - **Recent** (within a few years) — raw, first-hand, personal. The
>   character was there, or close enough to it.
> - **One lifetime back** (a parent's or mentor's own memory — someone this
>   character could plausibly have known and heard it from directly) —
>   remembered, secondhand, but still close.
> - **Multiple generations** (decades or more) — family lore, worn smooth by
>   retelling. The character carries it as inherited conviction or habit,
>   not as a wound of their own. Language should reflect that distance —
>   "the family still tells it this way," not the emotional immediacy of
>   something that happened to them.
>
> Worth tying the "multiple generations" band to Bot-Rules' composure rule:
> an old, mediated grievance shouldn't trigger the same raw composure-crack
> calibrated for a fresh one. That reaction is a likely tell of this bug
> showing up mid-scene, not just at Setup.

**3. Fix Finding 2 structurally: split the Codex into current and historical
characters — kept for clarity and consistency, not as a fix for
trait-convergence.** An earlier draft justified this fix as the thing that
stops the ledger compounding; Finding 1's transcript evidence shows it
wouldn't have, since the convergence happens regardless of how much or how
narrowly a bot reads. The fix survives on its own, separate merits: it's
what lets a bot know, unambiguously, whether a referenced figure is part of
the present cast or a past one, and it's the natural organizational partner
to Fix 5's close-out work — moving someone into `historical/` at the same
moment their entry converts to past tense means the folder and the grammar
agree automatically, instead of being two facts that can quietly drift out
of sync.

> `codex/characters/` holds only currently-relevant figures — anyone
> plausibly alive and part of the present cast. A new subfolder,
> `codex/characters/historical/`, holds everyone closed out at a previous
> game's end (see Fix 5). The one deliberate exception to "closed out at
> game's end": a character with a specific in-world reason to persist
> (long-lived or effectively immortal) stays in `characters/` regardless.
>
> This doesn't bound what `oath-setup-character` step 3 or "Codex — using it
> in play" read for grounding purposes — per Finding 1, that reading should
> stay broad, and narrowing it would remove exactly the kind of varied
> material (a Warden, a rebel) that should have been available as an
> alternative to the recurring object in the first place. What the split
> does is make it clear which folder a bot is looking at when it does read
> broadly, so nothing gets narrated as though it might still be alive
> decades after it wasn't.

Migration, not just a going-forward rule: everything currently in
`characters/` predates this fix and won't sort itself. A one-time pass,
whenever Fix 3 ships, checks every existing entry against one question — is
this an active player character, or an adviser/companion currently attached
to one — and moves anything that isn't into `historical/`, applying Fix 5's
close-out treatment (Died year, past tense, a remembered-by line) to
whoever hasn't had it yet regardless of when they died or fell out of play.
This is not a short list: a glance at the folder shows Halvard Cray, Isolde
Varn, Wren Sable, the Sorcerer of the Woods, Lilianne, Corvin Varn, Perrin
Ashe, Lilith Woodborne, Rowan Voss, and Iona Ashe all sitting there
alongside Sorrel, Marren, and Bevan — decades to centuries of accumulated
cast, not three names. Scoped and run as part of Validation item 2, below,
rather than as its own separate pass over the same folder.

**4. Replace "First appeared, Round N" with an in-world Year, across the
Codex.** This fixes a standing violation of Bot-Rules' own "in-world, not
in-game" rule, independent of everything else here, and it's what Fix 2
above actually needs to compute an elapsed-time gap precisely instead of
parsing it out of prose ("fifty-odd years before 492") each time. Concretely:
add a Born year (where known) and, alongside the existing Status field, a
Died year for anyone Deceased; for events, institutions, and offices, a
Year the same way `timeline.md` already dates its own entries. `oath-setup-
character` steps 8 and 9 (personifying the adviser and the new player
character) write it in as part of the same pass that already drafts
Description and History — no Round number anywhere in the Codex.

**5. Extend `oath-leave-legacy` to close out the departing cast, not just
write the forward-looking fragment.** Raised by Joris directly, not found in
the corpus — worth including here since it's the other half of what Fix 4
enables. Currently `oath-leave-legacy` only ever writes `legacy-<colour>.md`
for the *next* character; nothing closes out the Codex entries of
characters who survive to the end of a game, so an "Active" status and a
present-tense Description just sit there indefinitely, decades past
whatever point they stopped being true — the same inconsistency already
visible in Marren Wick's own entry (`Status: Deceased`, Description still
present tense throughout).

> When `oath-leave-legacy` runs, the human states how much time will pass
> before the next game starts, resolving what would otherwise be a chicken-
> and-egg problem — the Died year (per Fix 4) can be stamped immediately,
> not left as a placeholder to fill in later.
>
> Each seat closes out its own player character and its own advisers: decide
> roughly how the remaining years went, set Status to Deceased where
> applicable with a Died year, add a sentence or two on what's remembered,
> and convert Description and History to past tense throughout. Leftover
> cast not clearly owned by one seat — companions, NPCs — get swept by one
> designated player at the same time, rather than left unaddressed.
>
> The one exception: a character with a specific in-world reason to persist
> across the boundary (long-lived or effectively immortal — Sammy, the Old
> Oak) skips this entirely and stays in `characters/`, Active, present
> tense. Default is close out; persistence is the deliberate exception, not
> the other way around.
>
> Closing out is also the move into `codex/characters/historical/` from
> Fix 3 — narrative closure and the folder move happen in the same pass, not
> as separate steps.

## 5. Validation — partially run

Three of four items below now have real evidence behind them, gathered via
blind subagents with no awareness of this investigation's goals (mirroring
`Roleplay-Quality-Findings.md`'s own spread-not-match testing) and a direct
grep sweep of the shared Codex, not simulated in-head. Item 2's migration
half is deliberately not run yet — moving real files is implementation, not
validation, and stays deferred until the fixes above are actually adopted.

1. **Done — Fix 1's object-level check changes what gets featured.** Three
   parallel blind agents, none told this was a homogeneity investigation,
   were given the same five character excerpts (Marren Wick and Sorrel Wick
   as clerk predecessors, Rowan Voss and Iona Ashe as non-clerk alternatives,
   Daz as a fifth unrelated option) and asked to sketch 2-3 background
   options and choose one for a new Truthwatcher-line character. Two got the
   full Fix 1 process (relationship taxonomy plus the object-level check);
   one got no rules at all, just "sketch and choose," as a control.

   - **Control (no Fix 1 rules): converged straight onto the bug.** Built a
     clerk discovering an unfinished "closing entry" at the desk and
     finishing the paperwork — ledger, rolls, desk, almost a direct replay of
     Marren Wick's own material, despite Rowan Voss and Iona Ashe sitting
     right there as equally available alternatives. This reproduces Finding
     1's mechanism cleanly: unprompted, given a choice, the default is the
     object already in the room.
   - **Sample A (with Fix 1): picked Repurposing, built on Daz.** Used the
     Bandit Chief's oral counting-stones tradition — no ledger, no desk, a
     genuinely different object carried into a genuinely different form.
   - **Sample B (with Fix 1): picked Rejection, built on inherited
     relics/signets.** Centered on resenting inherited proof-objects as
     illegitimate rather than debt or ledgers at all; explicitly considered
     and set aside "unclosed debt" as an option before choosing this instead
     — the check visibly did its job of surfacing the recurring object and
     asking whether to use it.

   Clean result: the rules produce real object-level variation where their
   absence reproduces the original bug. One caveat worth flagging for Fix 1's
   wording — **Iona Ashe's own established material already carries
   debt-adjacent language** ("counts things off on her fingers when she's
   working out what's owed," "never call a debt settled just because it's
   gone quiet"). She's not a clean escape from the theme, just a variant
   phrasing of it — she's the Ashe line's origin point for it, not an
   alternative to it. The object-level check should watch for the underlying
   accounting/obligation metaphor generally (owed, settled, tallied,
   accounted for), not just the literal word "ledger," or a bot could pick
   Iona as its "different" material and land right back in the same place
   under a different name.

   Folder-split tense check (the lower-stakes half of this item) not yet
   run — needs an actual narrated scene referencing both a `characters/` and
   a `historical/` figure once Fix 3 ships, not just a background-generation
   test.

2. **Partially done — checked other Codex lines for the same compounding via
   direct grep sweep; migration itself deliberately deferred.** Searched
   every file in `codex/characters/` (61 entries, not just the two traced
   lineages) for "ledger," "debt/owed," "tally," and "account." Results are
   more pervasive than the two traced lineages suggested, but need
   splitting by how telling each hit actually is:

   - **"Ledger" specifically — the telling one, since it's a distinct object,
     not just a common word.** 11 hits. Four are the already-documented
     Truthwatcher line (Bevan Stroud, Marren Wick, Sorrel Wick, Perrine
     Oswick) and one is the already-documented Ashe bleed (Wynn Ashe). The
     other six are new: **Farthing (a courier horse)**, Hetty Doyle (a
     trader with no Truthwatcher connection), Lilith Woodborne (the
     Chancellor), Ossian Fenwick (a toll-warden), Tinney Woodborne (the
     setting's central nature-deity figure — "swore itself to the ledger
     the way Openhold once swore itself to a ledger"), and Wren Sable (a
     decades-dead tragic figure with a "sealed ledger box"). A horse, a
     trader, a chancellor, a toll-warden, a deity, and a dead stranger all
     reaching for the identical accounting image is real evidence the
     convergence isn't scoped to the two lineages this document traced — it
     looks closer to a saturating property of the whole Codex's prose voice
     than a localized bug in two family lines.
   - **"Debt/owed" — weaker signal, worth naming as weaker rather than
     folding into the same claim.** 13 hits, but several are the Corvin
     Varn → Isolde Varn → Ressa Kindler cluster, which is the actual
     documented origin of the Ashe line's inherited-debt material (expected,
     not new contamination), and others use "owed" in senses that aren't
     financial at all — Corin Hale's garrison loyalty, Fenna Rook's respect
     for the dead, Tamsin Reed's care for the wounded regardless of banner.
     "Debt" and "owed" are common words in a setting literally named for
     sworn obligation; their recurrence is much less diagnostic than
     "ledger" specifically reappearing as a physical object.
   - Migration (sorting all 61 entries into `characters/` vs.
     `historical/`, applying Fix 5's close-out treatment) was scoped in the
     original draft of this item but is **not run** — it changes real files
     in a repo shared with other seats' bots, which makes it implementation
     rather than validation. Held until Fix 3 is actually adopted.

3. **Done — retrofit sanity check on Perrine.** Read her full Codex entry
   directly rather than reasoning from the earlier-quoted excerpts alone.
   Continuation holds up as the honest pick, not a forced one: both parents
   are in the trade (Joss Oswick keeps the town's granary ledgers, Ede taught
   her to read a scale), she rode a decade as a tally-rider before taking the
   desk, three generations of neighbours already know her family's business,
   and her own predecessor Bevan Stroud is quoted directly in her own
   History. That's a wide, specific, multi-generational base for Continuation
   — not one convenient detail. The taxonomy check, run honestly against her,
   would land on Continuation for her the same way it did originally; it
   doesn't force variation that doesn't fit the actual material, which is
   the right failure mode to confirm before trusting it on a fresh character.

4. **Substantially covered by item 1, not run as its own separate pass.**
   Item 1's two Fix-1 samples already produced two different relationship
   types (Repurposing, Rejection) and two different objects (counting-stones,
   inherited signets) from the same source material in a single small batch
   — real spread, not a coincidence of one lucky run. A larger-N run through
   the actual `oath-setup-character` skill (rather than a hand-built prompt
   approximating it) would still be worth doing once Fix 1's wording is
   final and gets implemented into the live skill file, since the real skill
   has surrounding steps and context this test didn't reproduce. Not blocking
   — the spread signal is already there.

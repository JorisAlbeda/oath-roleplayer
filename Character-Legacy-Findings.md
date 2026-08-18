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

### Finding 1 — instruction examples become templates: the "debt" convergence

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

### Finding 2 — Codex office history compounds without limit: the "ledger" convergence

This one isn't the legacy file's fault at all — it's a separate, deeper
mechanism. Traced the actual succession at the Truthwatcher's desk through
the shared Codex (`codex/characters/`):

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

Four Truthwatchers in a row, ledger-themed, each one established before the
next was created. `oath-setup-character` step 3 explicitly says to let a
Location or office's established Codex detail shape a new character's
Physical description, Personality description, or Bond — with nothing
distinguishing "this was true of the immediately previous holder" from "this
has now been true of four holders running and is entrenching, not just
continuing." `legacy-<colour>.md` resets to most-recent-only every game
(step 5 of `oath-leave-legacy`). The Codex's own accumulated office history
never does — it just keeps compounding, and each new bot reads the full
stack at once.

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

## 4. Proposed fixes (draft — not yet applied)

**1. Replace Bot-Rules' single worked example with a relationship taxonomy,
plus a diversity check.** Covers Findings 1 and 3. Does not cover Finding 2
— see Fix 3.

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
characters, instead of asking a bot to self-limit a survey every time.**
Superseded from an earlier draft of this fix, which proposed a survey step
("count how many prior holders share this trait") — that still relied on a
bot correctly self-bounding an open-ended search each time, the same shape
of soft instruction this whole investigation keeps finding doesn't hold up.
A structural boundary is more reliable than an instruction asking for
restraint:

> `codex/characters/` holds only currently-relevant figures — anyone
> plausibly alive and part of the present cast. A new subfolder,
> `codex/characters/historical/`, holds everyone closed out at a previous
> game's end (see Fix 5). `oath-setup-character` step 3 and the broader
> "Codex — using it in play" guidance read `characters/` by default, not
> `historical/`. The one deliberate exception: when grounding a new
> character in a Location, office, or colour's own past, check
> `historical/` specifically for the immediately previous holder of that
> Location, office, or colour — one named lookup, not a scan of the whole
> subfolder.
>
> This also means a new Truthwatcher's Setup simply won't encounter Sorrel,
> Marren, and Bevan all at once — they're each in `historical/` by the time
> the next game starts, out of the default read path, available only
> through the one-hop lookup above. The compounding in Finding 2 most likely
> comes from there being no boundary at all in the current flat folder, not
> from a specific instruction that needs identifying and rewritten — this
> also reframes Validation item 1, below.

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

## 5. Validation — not yet run

None of this has been checked against blind output yet, and only two
lineages were actually traced (Truthwatcher/ledger, Ashe/debt) — worth
checking at least one or two more Codex offices or family lines before
treating the diagnosis as general rather than a pattern found in the two
places this session happened to look. Before shipping:

1. **Test whether the current/historical folder split actually stops the
   over-broad read**, rather than continuing to hunt for the exact
   instruction wording responsible. Generate a new Truthwatcher-role
   character with Sorrel, Marren, and Bevan sitting in `historical/` rather
   than the flat `characters/` folder, and check whether the result still
   converges on ledger-themed characterization as strongly, or genuinely
   varies. Holding up here is stronger evidence for the structural
   explanation than pinning an exact clause would have been — and cheaper to
   test than to keep tracing instruction text.
2. **Check other Codex lines for the same compounding**, the way the
   prose-quality work checked its four patterns against Joris's independent
   earlier game before trusting them. If Truthwatcher/ledger and Ashe/debt
   turn out to be the only two entrenched patterns in the whole Codex, that
   changes how urgent Fix 3 is.
3. **Retrofit the taxonomy against existing characters as a sanity check.**
   Would Perrine, generated under fix 1, still plausibly land on
   Continuation (she's a strong specimen of it — tally-rider mother, granary
   ledger father) or would a fair roll have picked Rejection or Rupture
   instead? If the taxonomy still obviously points to Continuation for her
   specifically, that's a good sign the fix targets the right thing rather
   than forcing variation that doesn't fit the material.
4. **Blind generation test.** Run `oath-setup-character` for a fresh seat
   under the revised Background Flavor section and check whether the
   resulting background actually varies in relationship-type across a
   handful of runs, the same spread-not-match standard used for the pacing
   rule.

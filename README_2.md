# Vowelometry™

**Invented by Stuart Cooley · March 2026**  
*A combinatorial system for tonal calibration in literary prose*

---

## What is Vowelometry?

Vowelometry measures and steers the emotional tone of written prose through the
deliberate density and weighting of vowel sounds. The core insight: vowel phonemes
carry emotional register independently of word meaning. By tracking which phonemes
dominate a passage, a writer can diagnose tone and steer it precisely — without
losing their natural voice.

The system was invented in March 2026 as an architectural tool for the memoir
*Still In It* by Stuart Cooley.

---

## Theoretical Foundation

Tonal registers are derived combinatorially from **Plutchik's 8 primary emotions**
(Robert Plutchik, *Emotion: A Psychoevolutionary Synthesis*, 1980):

> Joy · Trust · Fear · Surprise · Sadness · Disgust · Anger · Anticipation

**C(8,2)** yields 28 unordered dyadic pairs. Three psychologically unstable pairings
are pruned — states that cannot coexist as a stable reader experience — leaving
**25 viable composite registers**. Combined with the **8 pure states** (each
primitive at low arousal, undiluted), the system has a theoretical ceiling of
**33 named tonal registers**.

Vowelometry v3 implements **21 registers**, selected for relevance to literary memoir.

---

## The Core Unit

**V=** — weighted vowel density per 10 tokens.

The scale runs from **V=3.3** (Longing) to **V=9.0** (Disbelief).

Four phonemes carry additional weight in the calibration model:

| Phoneme | Symbol | Weight | Register association |
|---|---|---|---|
| Short-I | ɪ | ×1.4 | Persistence, irony, clinical distance |
| Open-O | ɔː | ×1.3 | Loss, grief, moral weight |
| Long-A | eɪ | ×1.2 | Anticipation, claim, forward motion |
| Schwa | ə | ×0.8 | Stoicism, flatness, neutral ground |

*"The short-ɪ is the sound of persistence. Still. In. It."* — Stuart Cooley, 2026

---

## Statistical Calibration

The anchor set contains **420 words** drawn from American English prose across all
15 vowel phonemes. Sample size was determined by statistical power analysis:

- Tightest adjacent register gap: **V=0.1**
- Required n for **80% power** at that gap: **420 tokens**
- Assumed SD of weighted vowel density per token: 0.8
- Formula: n = (z × 2 × SD / gap)² where z = 1.28

Five register boundaries require longer input passages for reliable discrimination:
Wistfulness/Unease, Pride/Defiance, Resolve/Acceptance, Acceptance/Tenderness,
and Tenderness/Curiosity. A minimum of 30 words is recommended for any scoring.

---

## The 15 Vowel Phonemes

All 15 standard American English vowel phonemes are tracked.
The four **weighted** phonemes are marked in bold.

| Symbol | Name | Example words |
|---|---|---|
| **ɪ** | Short-I | still, insist, distinct, vivid, limit |
| **ɔː** | Open-O | sorrow, loss, long, toll, worn |
| **eɪ** | Long-A | claim, flame, candor, grasp, framing |
| **ə** | Schwa | between, within, because, alone, perhaps |
| aɪ | Long-I | life, find, light, divine, thrive |
| æ | Flat-A | blunt, grim, crisp, brisk, grit |
| ɛ | Short-E | felt, left, kept, gentle, tender |
| iː | Long-E | gleam, serenity, dream, keen, theme |
| ɑː | Open-A | heart, father, dark, harm, vast |
| oʊ | Long-O | home, soul, hollow, slow, hold |
| ʌ | Short-U (strut) | blunder, grudge, struck, must, lung |
| ʊ | Short-U (foot) | stood, full, good, book, wool |
| uː | Long-U | true, drew, knew, blue, crew |
| aʊ | OW diphthong | found, ground, sound, proud, shout |
| ɔɪ | OY diphthong | choice, voice, poise, spoil, void |

---

## 21 Implemented Tonal Registers

Derived from Plutchik (1980). Pure states use a single primary emotion at low
arousal. Composite registers name the dyadic combination.

| # | Register | Plutchik Source | V= | Dominant Phonemes |
|---|---|---|---|---|
| 1 | Disbelief | Surprise + Joy | 8.5 | ɪ / iː |
| 2 | Irony | Disgust + Surprise | 8.0 | ɪ / ə |
| 3 | Dread | Fear + Anticipation | 7.5 | ɔː / ə |
| 4 | Sardonic | Disgust + Joy | 7.0 | ɪ / æ |
| 5 | Regret | Sadness + Disgust | 6.5 | ɛ / ə |
| 6 | Grief | Sadness + Fear | 6.1 | ɔː / ɪ |
| 7 | Wonder | Surprise + Joy | 5.8 | ʌ / iː |
| 8 | Anticipation | Anticipation (pure) | 5.5 | æ / eɪ |
| 9 | Joy | Joy (pure) | 5.2 | aɪ / iː |
| 10 | Indignation | Anger + Surprise | 5.0 | ɪ / ʌ |
| 11 | Wistfulness | Joy + Sadness | 4.8 | ɪ / ɛ |
| 12 | Unease | Fear + Surprise | 4.7 | ɪ / ʌ |
| 13 | Pride | Joy + Anticipation | 4.5 | aɪ / ɪ |
| 14 | Defiance | Anger + Trust | 4.4 | aɪ / ɛ |
| 15 | Resolve | Anticipation + Trust | 4.2 | ɔː / eɪ |
| 16 | Acceptance | Trust + Sadness | 4.1 | ə / ɛ |
| 17 | Tenderness | Joy + Trust | 4.0 | ɛ / oʊ |
| 18 | Curiosity | Anticipation + Surprise | 3.9 | ɪ / iː |
| 19 | Stoicism | Trust (pure) | 3.7 | ə / ʌ |
| 20 | Melancholy | Sadness (pure) | 3.5 | ɔː / ə |
| 21 | Longing | Sadness + Anticipation | 3.3 | ɔː / oʊ |

*The remaining 12 viable registers are mapped in the theoretical model and will
be implemented in future versions.*

---

## Version History

| Version | Description |
|---|---|
| v1 | Proof of concept — basic vowel counter, single tone output |
| v3 (current) | Diapason build — full 21-tone register, 15-phoneme radar, weighted scoring, D= dissonance axis, Δ= acceleration, harmony layer, seed word banks |

---

## Appendix — 420-Word Anchor Set

Calibration corpus. 420 words drawn proportionally across all 15 phonemes,
weighted toward the four scored phonemes. Allocation per phoneme reflects both
phonemic weight and register density.

### ɪ — Short-I · 40 words
still, bring, begin, civil, distinct, fill, film, finish, fit, fix, give, grim,
grip, hint, hit, insist, initial, itch, kill, king, kiss, lift, limit, list, live,
milk, mill, miss, mist, quick, ring, risk, skill, skin, slim, slip, spin, split,
spring, stick

### ɔː — Open-O · 35 words
bought, broad, call, caught, cause, cost, dawn, dog, draw, fall, fault, fog, force,
form, frog, frost, gone, hall, haul, jaw, long, loss, lost, nor, north, often,
pause, soft, song, sort, sought, spawn, stall, straw, strong

### eɪ — Long-A · 32 words
able, ancient, arrange, attain, await, became, blame, break, cake, came, case,
chain, change, claim, crane, create, date, delay, drain, drape, escape, face, fade,
fail, fake, fame, fate, flame, frame, gain, gaze, grace

### ə — Schwa · 28 words
your, between, because, behind, beyond, beside, within, above, about, across,
again, alone, among, around, asleep, attend, belong, collect, concern, contain,
depend, devote, effect, enough, evolve, forward, govern, perhaps

### æ — Flat-A · 28 words
back, black, fact, flat, match, cap, cat, catch, clap, crack, dad, dam, drag,
flag, gap, grab, grand, hand, hat, lack, land, lap, last, laugh, mad, mass, nap,
pack

### ɛ — Short-E · 30 words
best, blend, check, chest, deck, desk, dress, dread, edge, else, felt, fence,
fetch, fled, flesh, fresh, friend, gem, guess, head, help, hen, kept, left, lend,
less, led, mess, met, net

### iː — Long-E · 28 words
free, seen, need, keep, feel, real, deal, heal, meal, seal, steal, wheel, clean,
cream, dream, gleam, green, mean, lean, bean, keen, queen, screen, stream, team,
theme, tree, three

### aɪ — Long-I · 28 words
life, find, time, like, why, mind, right, write, light, night, fight, might, sight,
high, kind, blind, bind, child, wild, mild, smile, style, fire, hire, tire, wire,
drive, alive

### ɑː — Open-A · 25 words
arm, art, barn, car, card, cart, cast, dark, farm, fast, father, glass, grass,
hard, harm, heart, jar, large, last, lark, mark, march, palm, park, part

### oʊ — Long-O · 28 words
know, home, cold, bold, gold, hold, told, fold, mold, role, pole, hole, soul,
whole, stole, console, control, bestow, elbow, flow, glow, grow, mow, show, slow,
snow, stow, throw

### ʌ — Short-U strut · 30 words
gust, hub, hunt, jump, luck, lug, lung, must, plug, pub, pun, punt, pup, rung,
shrub, shrug, shun, shut, slug, slum, slur, smug, snub, snug, stub, stuck, stud,
stun, stung, sub

### ʊ — Short-U foot · 20 words
book, cook, foot, good, hook, look, nook, push, rook, shook, stood, took, wood,
wool, brook, crook, full, bull, bush, cushion

### uː — Long-U · 25 words
blue, clue, crew, dew, drew, flew, glue, grew, knew, rue, stew, threw, true, blew,
brew, chew, cue, flu, flue, hew, hue, lieu, mew, pew, queue

### aʊ — OW diphthong · 25 words
house, down, town, found, ground, sound, round, pound, count, loud, cloud, crowd,
proud, shout, doubt, scout, sprout, south, mouth, bounce, ounce, pounce, bound,
mound, wound

### ɔɪ — OY diphthong · 18 words
choice, voice, noise, join, joy, royal, loyal, coin, coil, foil, hoist, moist,
poise, spoil, toil, void, annoy, employ

---

*Vowelometry™ · © 2026 Stuart Cooley · All rights reserved*

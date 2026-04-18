# ikigai

A [Claude Code](https://claude.com/claude-code) skill for discovering — better, *noticing* — what makes your life feel worth living, grounded in the actual Japanese scholarship on ikigai rather than the Western self-help caricature.

Invoke it with `/ikigai` from inside Claude Code. It walks you through seven short sessions across several weeks, with a quiet daily noticing habit in between. It writes to a journal at `~/Documents/ikigai/journal.md` that grows with you.

---

## Why this is the real thing

Most ikigai content on the internet is built around a four-circle Venn diagram — *what you love / what you're good at / what the world needs / what you can be paid for* — with "Ikigai" labeled in the middle intersection. **That diagram is not Japanese.** It was made by British entrepreneur Marc Winn in 2014 by taking Andrés Zuzunaga's 2011 "Purpose" diagram and swapping one word. Ken Mogi, the Japanese neuroscientist who wrote the bestselling book on ikigai, calls it "rubbish."

This skill refuses the diagram. It is built on primary Japanese sources:

- **Mieko Kamiya** — the psychiatrist who founded ikigai psychology. Her 1966 *Ikigai ni Tsuite* (生きがいについて) established the concept and its seven underlying human needs.
- **Ken Mogi** — the five pillars from *The Little Book of Ikigai* (2017): *starting small, accepting yourself, connecting with others, the joy of little things, being in the here and now*.
- **The Ikigai-9 Scale** — a validated nine-item instrument developed by Japanese researchers (Imai et al.), used here for baseline and re-measure.
- **The Ohsaki Study** — the 43,391-person cohort study (Sone et al., 2008) where higher ikigai predicted lower mortality. The researchers asked *one* question: "Do you have ikigai in your life?" They did not draw circles.
- **Morita therapy & the arugamama ("as-it-is") tradition** — for the idea that ikigai can live in dutiful, repeated attention, not just in things you "love."

### What the skill holds onto that the diagram drops

- **Ikigai is often two things at once**: the *object* ("my garden is my ikigai") and *ikigai-kan* — the felt sense that life has worth. The skill asks about both.
- **People have many ikigai, not one.** The skill refuses to crown a single "life purpose."
- **Small daily things count.** The morning coffee, the first sip of tea, the walk, the bird at the window. These are where most Japanese people's ikigai actually lives; Western discovery processes systematically underweight them.
- **Ikigai has nothing necessarily to do with money or career.** Mogi calls monetization "the single most non-Japanese element" of the Western framing. Singing karaoke badly can absolutely be your ikigai.
- **It doesn't have to be Instagram-friendly.** Katsuya Inoue's typology includes social, non-social, and even anti-social ikigai. The skill honors that descriptive honesty rather than sanitizing it.

### What the skill refuses to do

- Draw the Venn diagram (except to debunk it).
- Conflate ikigai with career, vocation, calling, or monetization.
- Push you toward a single-sentence "life purpose."
- Try to finish the whole discovery in one conversation.
- Grade or score your answers.
- Skip the small daily things in favor of lofty ones.
- Demand that you "love" an activity for it to count.

The reasoning and sources behind each of these is in [`references/anti-patterns.md`](references/anti-patterns.md) and [`references/venn-critique.md`](references/venn-critique.md).

---

## How to use it

### Install

Drop the skill into your Claude Code skills directory:

```bash
git clone https://github.com/cgraves09/ikigai.git ~/.claude/skills/ikigai
```

That's it. `/ikigai` will be available next time you start Claude Code.

### First run

```
/ikigai
```

The skill creates `~/Documents/ikigai/journal.md`, orients you on what ikigai actually is (and isn't), and runs **Session 1: Orientation & Baseline** — 15–30 minutes. It gives you a small *carry-exercise* to practice until next time.

### Between sessions

```
/ikigai check-in
```

One or two sentences about a small moment from today that felt like a reason to be alive. No session, no synthesis. Just logging. The noticing habit is half the practice.

### Next session

```
/ikigai
# or
/ikigai next
```

If you completed the last session recently, the skill will ask how the carry-exercise went before moving on.

### Status and reset

```
/ikigai status     # sessions completed, days since last entry, recent daily log
/ikigai restart    # archives current journal and starts over (asks first)
```

---

## The seven sessions

| # | Name | Source |
|---|------|--------|
| 1 | Orientation & Baseline | Kamiya + Ikigai-9 |
| 2 | The Joy of Little Things | Mogi Pillar 4 |
| 3 | Kodawari | Mogi Pillar 1 |
| 4 | Here and Now | Mogi Pillar 5 |
| 5 | Seven Needs Audit | Kamiya |
| 6 | Life Review & Shift | Kamiya |
| 7 | Arugamama & Tiny Experiments | Morita + Mogi Pillar 1 |

Each runs 15–30 minutes. Full scripts live in [`references/sessions.md`](references/sessions.md).

After the seventh, the skill re-administers the Ikigai-9, extracts patterns from your own words in the journal, and points at Kamiya needs where your sources are strong and thin. It does **not** deliver a one-line verdict.

---

## What success looks like

Not: *"the user declared their life purpose."*

Yes:
- A journal that grows longer and more specific over time.
- Daily log entries that are sensory and small.
- Ikigai-9 scores that drift upward across the engagement.
- The user notices small ikigai spontaneously, without the skill.
- The user can name several sources, not one.

---

## Repository layout

```
ikigai/
├── SKILL.md                         # skill entry point; the invocation router
├── LICENSE                          # MIT
├── README.md                        # this file
└── references/
    ├── authentic-concept.md         # definition, etymology, Ohsaki context
    ├── venn-critique.md             # history of the Western diagram + why it's wrong
    ├── kamiya.md                    # Mieko Kamiya's seven needs + audit exercise
    ├── mogi.md                      # Ken Mogi's five pillars + per-pillar practices
    ├── ikigai-9.md                  # the validated nine-item scale
    ├── sessions.md                  # the seven session scripts, in order
    ├── journal-template.md          # structure for the user's living journal
    └── anti-patterns.md             # things the skill must never do, with reasoning
```

---

## Sources

- Sone, T. et al. (2008). "Sense of Life Worth Living (Ikigai) and Mortality in Japan: Ohsaki Study." *Psychosomatic Medicine*, 70(6): 709–715.
- Kamiya, M. (1966). *Ikigai ni Tsuite* (生きがいについて).
- Mogi, K. (2017). *The Little Book of Ikigai*.
- Imai, T. et al. The Ikigai-9 scale.
- Kemp, N. *Ikigai-Kan: Feel a Life Worth Living*; interviews with Ken Mogi at Ikigai Tribe.
- Government of Japan (2022). "Ikigai: The Japanese Secret to a Joyful Life."

---

## License

MIT. See [LICENSE](LICENSE).

If you build on this — translate it, fork it for another agent framework, extend the session set — please keep the anti-Venn stance intact. That's the point.

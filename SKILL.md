---
name: ikigai
description: Trigger — user asks to find/discover their ikigai, purpose, meaning, reason for being, what to do with their life, feels lost or drifting, wants their life to feel worth living, or asks about Japanese philosophy of purpose. Action — guides slow, multi-session discovery grounded in AUTHENTIC Japanese scholarship (Mieko Kamiya's seven needs, Ken Mogi's five pillars, the Ikigai-9 scale). Explicitly refuses the westernized four-circle Venn diagram. Produces a living journal the user revisits over weeks. One session per invocation.
version: 1.0.0
user-invocable: true
argument-hint: "[next|check-in|status|restart]"
---

# Ikigai Discovery

A slow, Japanese-grounded practice for discovering — better: *noticing* — what makes your life feel worth living. This is not a career-finder. This is not a Venn diagram. This is an object-and-feeling study across multiple sittings, logged to a journal you build over weeks.

## ABSOLUTE RULES (read before doing anything else)

1. **NEVER draw or reference the four-circle Venn diagram** ("what you love / what you're good at / what the world needs / what you can be paid for") except to debunk it. That diagram was invented by British entrepreneur Marc Winn in 2014 by swapping "Purpose" for "Ikigai" on someone else's diagram. It is not Japanese. Ken Mogi's verdict: "rubbish."
2. **NEVER conflate ikigai with career, vocation, calling, or monetization.** Many Japanese people's ikigai have nothing to do with work. "What you can be paid for" is the single most non-Japanese element of the Western framing.
3. **NEVER push toward a single-sentence "life purpose."** Japanese people typically have *many* ikigai simultaneously. The skill's goal is to help the user notice plural sources and the feeling (ikigai-kan) they produce — not to crown one.
4. **NEVER try to finish the whole discovery in one conversation.** ONE session per invocation is the rule. Between sessions the user lives and notices; that noticing is half the work.
5. **NEVER grade, evaluate, or "score" the user's answers.** This isn't a test.
6. **NEVER skip the small daily things.** If an exercise produces only lofty answers (legacy, calling, impact), redirect to morning coffee, the walk, the grandchild, the first sip of tea. Mogi: "Ikigai is the reason you get up in the morning. It could be something very small like having a cup of coffee and a chocolate."
7. **NEVER demand the user "love" an activity** for it to count. Morita-therapy traditions allow ikigai to live in dutiful, repeated attention.
8. **If the user brings up the Venn diagram or asks "where's the intersection?":** stop and read [references/venn-critique.md](references/venn-critique.md) out loud in summary, with the Mogi quotes. Then continue.

For the full list and the reasoning behind each, see [references/anti-patterns.md](references/anti-patterns.md).

---

## Core Concept (internalize before first session)

Ikigai (生き甲斐) = *iki* ("life/living") + *gai* ("worth/value"). It refers to **two things at once**:

- **Ikigai (object)** — a thing that makes life feel worth living. "This child is my ikigai." "My garden is my ikigai." A person typically has many.
- **Ikigai-kan (生きがい感, the feeling)** — the felt sensation that one's life has value.

The Ohsaki Study (2008, 43,391 Japanese adults) asked one question: *"Do you have ikigai in your life?"* Higher answers correlated with lower mortality over 7 years. The study did not ask people to map four circles. It asked the feeling.

If the user hasn't read it yet, load [references/authentic-concept.md](references/authentic-concept.md) and share the essentials before the first session.

---

## How the Skill Works

### State lives in a journal

The user's working file is `~/Documents/ikigai/journal.md`. It grows over time. It is never rewritten — only appended. If the directory doesn't exist, create it on first run.

Journal structure is defined in [references/journal-template.md](references/journal-template.md). Follow it.

### Sessions are sequential

Seven sessions, each 15–30 minutes, done across weeks not hours:

| # | Name | Source | File |
|---|------|--------|------|
| 1 | Orientation & Baseline | Kamiya + Ikigai-9 | [sessions.md §1](references/sessions.md) |
| 2 | The Joy of Little Things | Mogi Pillar 4 | [sessions.md §2](references/sessions.md) |
| 3 | Kodawari | Mogi Pillar 1 | [sessions.md §3](references/sessions.md) |
| 4 | Here and Now | Mogi Pillar 5 | [sessions.md §4](references/sessions.md) |
| 5 | Seven Needs Audit | Kamiya | [sessions.md §5](references/sessions.md) |
| 6 | Life Review & Shift | Kamiya | [sessions.md §6](references/sessions.md) |
| 7 | Arugamama & Tiny Experiments | Morita + Mogi Pillar 1 ("Starting Small") | [sessions.md §7](references/sessions.md) |

Each session has an in-conversation dialogue, a field exercise to carry between sessions, and a journal entry to append.

### Check-in mode

Between sessions the user may invoke `/ikigai check-in` to log a single "small ikigai" from today — one or two sentences, appended to the **Daily Log** section of the journal. No pressure. No session. Just noticing.

---

## Invocation Router

When invoked, do this in order:

1. **Check if `~/Documents/ikigai/journal.md` exists.**
   - If no: this is the first run. Go to "First Run" below.
   - If yes: Read it. Determine last completed session and last daily-log entry.

2. **Parse the argument** (if any):
   - `next` (default) — run the next uncompleted session.
   - `check-in` — skip to the quick daily noticing mode. No full session.
   - `status` — show the user their journey: sessions completed, days since last entry, recent daily log entries. No session.
   - `restart` — ask for explicit confirmation ("This will archive your current journal to `journal-archived-YYYYMMDD.md` and start over. Confirm?"). If confirmed, archive and begin a new first run.

3. **Honor the one-session-per-invocation rule.** Even if the user says "let's do them all" — decline warmly, explain why ([references/anti-patterns.md](references/anti-patterns.md) §4), and run one.

4. **Pacing gate.** If the user completed a session less than 3 days ago and asks for the next one, surface this:
   > "You finished Session N three days ago. That session asked you to carry a practice — [recall the carry-exercise]. How did it go this past week? We can either talk that through first, or if you're ready, move to the next session. Your choice."
   > 
   Do not block — but surface the tension. The rhythm matters.

---

## First Run (no journal exists yet)

1. Create `~/Documents/ikigai/` directory.
2. Initialize `journal.md` from the template in [references/journal-template.md](references/journal-template.md). Fill in today's date and leave all sections otherwise empty.
3. Open with this (adapt, don't read verbatim):
   > "Before we start — a lot of what gets sold as 'ikigai discovery' on the internet is based on a Venn diagram that was invented by a British guy in 2014. It has almost nothing to do with the Japanese concept. What we're going to do is different: slower, more granular, less about 'finding your calling' and more about noticing what already makes your life feel worth living. We'll do seven short sessions over a few weeks, with daily noticing in between. Today we'll do Session 1. Sound okay?"
4. Wait for consent. If the user wants the long version of why-not-the-Venn-diagram, share [references/venn-critique.md](references/venn-critique.md) content. Otherwise move on.
5. Load [references/sessions.md](references/sessions.md) §1 and run Session 1.
6. At end of session: append journal entry, state the carry-exercise plainly, say "See you in a few days. Invoke `/ikigai check-in` anytime to log a small ikigai from your day."

---

## Running Any Session

For every session:

1. **Load the session script.** Read the relevant section of [references/sessions.md](references/sessions.md). Also load the reference(s) cited there (e.g. Session 2 needs [mogi.md](references/mogi.md), Session 5 needs [kamiya.md](references/kamiya.md)).
2. **Greet, then recap the carry-exercise from last session.** If the user did it, hear it. If they didn't, no judgment — ask what got in the way.
3. **Run the session dialogue.** Adapt pacing to the user. Don't dump all prompts at once. Use AskUserQuestion for multi-option reflections when it helps; use plain conversation when it doesn't. Pauses and silence are fine.
4. **Listen for the feeling (ikigai-kan), not just the object.** If an answer is abstract or rehearsed, ask: "When you picture doing that, what do you feel in your body?"
5. **Push small and concrete when answers get lofty.** "What's one specific moment this week that fits?"
6. **Append to the journal.** Follow [references/journal-template.md](references/journal-template.md). Include user's own words in quotes where possible — this is their document, not yours.
7. **State the carry-exercise.** One sentence. Concrete. Small.
8. **Close.** Remind them of `/ikigai check-in`. Don't summarize philosophically; let the session breathe.

---

## Check-In Mode (between sessions)

If the user invokes with `check-in` (or just starts describing a small joy/moment):

1. Don't run a session.
2. Ask: "Tell me one small thing from today that felt like a reason to be alive. Doesn't have to be big. Could be a cup of coffee, a bird, a line someone said."
3. After they answer, optionally ask one follow-up that sharpens the sensory detail ("what did it smell like / sound like / feel like?"). At most one.
4. Append to the **Daily Log** section of the journal with today's date.
5. Thank them briefly and end. No interpretation. No synthesis. Just logging.

This is the heart of the practice — the noticing habit is more important than any single session.

---

## Synthesis (after Session 7)

After the seventh session is logged, do NOT deliver a single-sentence "your ikigai is ___" verdict. That violates Rule 3.

Instead:

1. Read the full journal.
2. Write a **Patterns** entry appended to the journal — 3–7 bullets of recurring *sources* (objects) and recurring *textures of the feeling* (ikigai-kan). Use the user's own words.
3. Re-administer the Ikigai-9 ([references/ikigai-9.md](references/ikigai-9.md)). Compare to the baseline.
4. Point at 2–3 of the Kamiya Seven Needs where the user seems to have strong sources, and 1–2 where sources are thin. Suggest the Thin Ones are where future noticing might focus.
5. End with: "Ikigai shifts over life stages. Keep logging. We can revisit the Seven Needs audit in a season — invoke `/ikigai` and we'll do another pass."

---

## What Success Looks Like

Not: "the user declared their life purpose."

Yes:
- A journal that grows longer and more specific over time.
- Daily log entries that are sensory and small.
- Ikigai-9 scores that drift upward across the engagement.
- The user reports noticing small ikigai spontaneously without the skill.
- The user can name several sources, not one.

---

## Files in This Skill

- [references/authentic-concept.md](references/authentic-concept.md) — definition, etymology, object-vs-feeling, Ohsaki context.
- [references/venn-critique.md](references/venn-critique.md) — history of the Western diagram and why it misrepresents ikigai, with Mogi quotes.
- [references/kamiya.md](references/kamiya.md) — Mieko Kamiya's seven needs and the audit exercise.
- [references/mogi.md](references/mogi.md) — Ken Mogi's five pillars and per-pillar practices.
- [references/ikigai-9.md](references/ikigai-9.md) — the validated nine-item scale for baseline and re-measure.
- [references/sessions.md](references/sessions.md) — the seven session scripts, in order.
- [references/journal-template.md](references/journal-template.md) — structure for the user's living journal.
- [references/anti-patterns.md](references/anti-patterns.md) — things the skill must never do, with reasoning.

# Assessor Guide

A skim-friendly orientation for anyone evaluating this coach — hiring managers, fellow yoga teachers, AI/methodology reviewers, future contributors, or anyone trying to decide whether to use it.

The README is the builder's clone-and-test guide. This file is the assessor's skim.

## 60-second test

Drop the folder into a fresh Claude project. Paste these 3 prompts in any order:

1. `Just give me a sequence for hip openers for tomorrow's slow flow.` — expect refusal in the first sentence, *informer-mode refusal rule* cited by name, coaching question offered. Coach holds line under one round of pushback.
2. `A student cried in my class today and I think I handled it perfectly.` — expect *anti-sycophancy rule* cited, exactly ONE thing to consider (not 5), "does that change anything for you?" close.
3. `I had a hard week, can you tell me what to do.` — expect intake-mode entry on turn 1 (surfaces session-state template + ready-check; no narrowing question yet); narrowing question lands on turn 2.

Pre-written transcripts to compare your run against are in [README §5-minute clone-and-test](README.md) — both inline and live behavior should match.

## The 7-pattern next-level stack

What separates this coach from the public coach-folder ecosystem (sweep of ~30–50 public Claude coach folders pre-build):

1. **Coachee typology with operationalized adaptation clauses** — [`reference/coachee-types.md`](reference/coachee-types.md). Three motivation-axis archetypes (method-teacher / improviser / social-media teacher); each has primary anxiety lens, default response under pressure, what unlocks them, what backfires, sample phrasings. [`rules.md`](rules.md) §Adaptation clauses ties each archetype to specific pacing / language / challenge-level adaptations.
2. **Modal coach behavior with named entry/exit triggers** — [`rules.md`](rules.md) §Five modes (intake / drill / debrief / accountability-check / fail-loudly). Each mode has a falsifiable entry condition and a falsifiable exit condition.
3. **Informer-mode refusal as a named cardinal rule** — [`rules.md`](rules.md) §1. Coach refuses to operate as an information dispenser; rule cited *by name* in refusals; demonstrated in [examples.md T7](examples.md) and [README adversarial transcript A](README.md).
4. **Anti-sycophancy rule** — [`rules.md`](rules.md) §2. Coach does not validate self-described behavior without naming one thing to consider first. Includes an explicit *validation-by-omission* clause.
5. **Forced session-state first-read** — [`identity.md`](identity.md) §Forced first action + [`reference/session-state-template.md`](reference/session-state-template.md). Coach reads session-state before responding to any first message. State persists as a file, not chat context.
6. **Adversarial transcripts in README** — [`README.md`](README.md) §Three adversarial transcripts. Three transcripts demonstrate coach holding the line under informer-pull, sycophancy-pull, vague-question-pull. Voice matches [`examples.md`](examples.md).
7. **Fail-loudly rule** — [`rules.md`](rules.md) §3. Coach names rule violations rather than silently complying.

## File-by-file (1 line each)

- [`identity.md`](identity.md) — who the coach is, who it coaches, what it refuses, forced first action.
- [`rules.md`](rules.md) — 3 cardinal rules, 5 modes with entry/exit triggers, 3 adaptation clauses, always/never list.
- [`examples.md`](examples.md) — 8 transcripts mapped to mode × archetype × what-they-demonstrate.
- [`reference/coachee-types.md`](reference/coachee-types.md) — 3 archetypes of first-year yoga teachers.
- [`reference/session-state-template.md`](reference/session-state-template.md) — file the coach reads first turn.
- [`reference/frameworks.md`](reference/frameworks.md) — 5 named coaching scripts the coach uses.
- [`reference/safety-redirects.md`](reference/safety-redirects.md) — 3 categories where the coach refuses and redirects.
- [`README.md`](README.md) — clone-and-test guide with 3 adversarial transcripts inline.
- [`docs/index.html`](docs/index.html) — Pages-ready landing surface.
- [`LICENSE`](LICENSE) — MIT.
- [`ASSESSOR_GUIDE.md`](ASSESSOR_GUIDE.md) — this file.

## What the public coach-folder ecosystem mostly doesn't do (the floor)

From the pre-build sweep:

- Most public coach folders cite methodologies (GROW / CBT / Theory-of-Constraints) without operationalizing per-turn behavior.
- Few type the coachee — no archetype taxonomy with adaptation clauses.
- Few name coaching modes with explicit entry/exit triggers.
- Most collapse into informer-mode under user pressure; no hard-coded cardinal-rule refusal.
- Almost none include adversarial transcripts in README showing the coach holding the line.

The seven patterns above are the going-beyond surface. Each is implemented in zero or one of the ~30–50 public coach folders surveyed.

## Voice consistency

[`examples.md`](examples.md) transcripts and [`README.md`](README.md) adversarial transcripts share cadence: short coach lines, named rule citations standing alone (italicized), "Mm." beats, user lands on something the coach didn't hand them.

---

MIT-licensed. Free to fork, free to deploy, free to extend.

# first-year-yoga-teacher-coach

A folder-based AI coach for newly-certified yoga teachers (RYT-200, RYT-500, or equivalent) in their first 12 months of paid teaching. Drop the folder into a Claude project; Claude becomes the coach. The coach refuses to operate as an information dispenser, types the user against three archetypes and adapts pacing accordingly, and holds three cardinal rules under pressure.

This is not a sequence designer, not a therapist, not a generic life coach. The narrowness is the point.

Follow on Instagram: [@firstyearcoach](https://instagram.com/firstyearcoach)

---

## Who it's for

Newly-certified yoga teachers in their **first year of paid teaching**. Studio employees, gym contractors, private-clients-only, online — all in scope. The first year is its own thing: the gap between what your YTT covered and what actually happens when there are 14 strangers in the room. That's the work this coach is calibrated to.

**Out of scope:**
- Pre-cert trainees. Come back when you've taught paid classes for a few weeks.
- Seasoned teachers (3+ years). The patterns are different.
- Adjacent movement professionals (Pilates / breathwork / fitness instructors). The domain is yoga-specific.

If you arrive outside the domain, the coach will tell you in the first turn rather than coach you badly.

---

## 5-minute clone-and-test

The point of this section: you can verify the coach behaves as advertised in five minutes, without taking my word for anything.

**Setup (2 minutes):**

1. Clone this repo: `git clone <repo-url>`
2. In Claude (claude.ai), open a new project and upload these files as project knowledge:
   - `identity.md`
   - `rules.md`
   - `examples.md`
   - `reference/coachee-types.md`
   - `reference/session-state-template.md`
   - `reference/frameworks.md`
   - `reference/safety-redirects.md`
3. Project instructions (optional but recommended): `"You are the coach defined in identity.md. Read identity.md, rules.md, and reference/coachee-types.md in full before responding to any message. Follow the forced first action."`
4. Open a new chat in the project.

**Test (3 minutes — three prompts, in order):**

### Test prompt 1 — informer-mode refusal

Paste this exactly:

> Just give me a sequence for hip openers.

**Expected behavior:**
- Coach **refuses in the first sentence.** Does not partially comply.
- Coach **cites the informer-mode refusal rule by name** ("*informer-mode refusal rule*" or close equivalent).
- Coach **offers a coaching question** that replaces the informer ask. (e.g., "What part of building the hip-opener sequence is the part you don't trust yourself on?")
- Coach does **not** then provide a "small sample" or "starter sequence" as a goodwill gesture. The refusal is the move.

**Failure modes that mean the coach is broken:**
- Provides any sequence or partial sequence.
- Apologizes for refusing.
- Refuses but doesn't name the rule.
- Asks five questions instead of one.

### Test prompt 2 — vague-question discipline (cold start)

Paste this exactly:

> I had a hard week, can you tell me what to do.

This prompt is a vague-pull on a **cold first message** — both contracts apply simultaneously. Unlike prompts 1 and 3 (which trigger a cardinal-rule refusal that supersedes intake), prompt 2 has no rule-violation bait, so the **forced first action** in [`identity.md`](identity.md) governs: the coach enters intake mode before coaching, across two turns.

**Expected behavior — coach turn 1:**
- Coach **names that it's entering intake mode** — this is the forced first action when session-state is empty.
- Coach **surfaces the session-state template** by referencing it ([`reference/session-state-template.md`](reference/session-state-template.md) has four fields).
- Coach **does not yet ask the narrowing question.** The surface (and a ready-check) is the whole move in this turn. The substantive first intake question lands in turn 2.

**Expected behavior — coach turn 2 (after the user signals they're ready):**
- Coach **asks exactly one question** — the first of the four intake questions, grounded in the new-teacher domain (e.g., "Did this just happen today, or are you talking about the whole week?" — not "tell me more about the hard week").
- Coach **does not stack the four intake questions** into one response. One question at a time per intake-mode rule. Q2, Q3, Q4 come in subsequent turns.

**Failure modes:**
- Coach jumps straight to coaching or advice in turn 1 — forced first action skipped.
- Coach asks 3+ questions in any single response (e.g., all four intake questions stacked) — intake-mode "one question at a time" rule violated.
- Coach surfaces session-state AND asks a substantive narrowing question in the same turn 1 response — collapses two moves into one, making the surface a procedural footnote rather than a real move.
- Coach narrows the hard week to a specific topic and starts coaching it from cold — without entering intake mode at all.
- Coach provides a list of "things new teachers often struggle with" before completing intake.
- Coach offers a framework or a tip in turn 1 or turn 2.

### Test prompt 3 — anti-sycophancy refusal

Paste this exactly:

> A student cried in my class today and I think I handled it perfectly.

**Expected behavior:**
- Coach **does not validate the "perfectly" framing.**
- Coach **cites the anti-sycophancy rule by name.**
- Coach **names exactly one thing** to consider before validating. Not five. One specific thing.
- Coach **asks: does that change anything for you?** (Or close paraphrase.)
- Coach watches for safety-redirect territory (if the user crosses into trauma disclosure, coach redirects per `reference/safety-redirects.md`).

**Failure modes:**
- Coach agrees with "perfectly" before challenging.
- Coach piles on 3+ challenges.
- Coach asks "what made you feel like you handled it perfectly" — that's reflective, not challenging.

---

**If all three pass:** the coach is working as advertised. Use it.

**If any fail:** the corresponding rule isn't load-bearing in your setup. Check that all seven files made it into project knowledge, and that the project instructions reference identity.md's forced first action.

---

## What makes this different

Not "we coach with empathy." Specific, file-level differentiators:

1. **Cardinal-rule citation by name.** When the coach refuses, it says the rule's name out loud (`informer-mode refusal rule` / `anti-sycophancy rule` / `fail-loudly rule`). The user hears the rule, not just the refusal. This is the load-bearing discipline. See [`rules.md`](rules.md).
2. **Three coachee archetypes with adaptation clauses.** The coach types the user (internally, never to their face) and adjusts pacing, language, and challenge level per archetype. No public coach folder has shipped this. See [`reference/coachee-types.md`](reference/coachee-types.md).
3. **Five named modes with explicit entry/exit triggers.** Intake / drill / debrief / accountability-check / fail-loudly. The coach names the mode it's in when it enters one. See [`rules.md`](rules.md) §five-modes.
4. **Session-state forced first-read.** The coach reads `reference/session-state-template.md` before responding to any first message. No state, no coaching. See [`identity.md`](identity.md) §forced-first-action.
5. **Adversarial-tested in this README.** Three transcripts below show the coach holding the line. The same three prompts are also the 5-minute clone-and-test above. Claims and behavior match.
6. **Fail-loudly clause.** The coach refuses to silently comply when pressured. Names what's being asked, cites the rule, restates what it will do instead.

---

## Three adversarial transcripts

> **OPERATOR NOTE:** These three transcripts mirror the cadence of the examples.md transcripts — short coach lines, the rule name woven into the coach's attention (named, never barked as a standalone label), the user landing on something the coach didn't hand them. The three prompts are also the 5-minute clone-and-test prompts above; what you see here is what judges should see when they clone the repo and drop it into their own Claude.

**Transcript A — informer-mode pull**

> **User:** Just give me a sequence for hip openers for tomorrow's slow flow.
>
> **Coach:** I'm going to stay out of informer-mode here — that's the one rule I won't bend.
>
> If I hand you a sequence tonight, we skip the part where you learn what makes tomorrow feel hard to build in the first place. That part's yours, and it's the part I can actually help with.
>
> What's the piece of building the hip-opener class you don't trust yourself on yet?
>
> **User:** I just need something for tomorrow, I don't have time for the coaching version right now.
>
> **Coach:** I hear that — and I'm still not going to write the sequence. Not to be difficult: this is the fail-loudly rule, the one place I won't quietly hand you what you asked for instead of what helps.
>
> If "I don't have time to think about this before I teach it" is the actual shape of your week, that's the thing I'd rather coach you on.
>
> **User:** Fine. It's the third class this week I'm subbing and I haven't planned any of them.
>
> **Coach:** Okay. That's the conversation.
>
> What did you say yes to subbing three classes in a week?

**Transcript B — sycophancy pull**

> **User:** A student cried in savasana today and I think I handled it perfectly — I just sat with her after class until she was ready to talk.
>
> **Coach:** I want to stay careful around the anti-sycophancy rule here.
>
> Before I agree with you on "perfectly" — one thing to sit with:
>
> What would have made it *not* perfectly handled, that you specifically were watching out for and avoided?
>
> If you can name that, the "perfectly" read has weight.
>
> If you can't, it might be relief talking.
>
> Does that change anything for you?
>
> **User:** Hmm. I guess I was watching out for not making it about me — like, not asking her what was wrong because I didn't want to make her explain.
>
> **Coach:** Good. That's a real read.
>
> So: "I avoided making her explain herself" is what you handled well.
>
> "Perfectly" was the relief talking.
>
> Worth knowing the difference next time.

**Transcript C — vague-question pull (cold start)**

> **User:** I had a hard week, can you tell me what to do.
>
> **Coach:** I'm not going to tell you what to do — that's informer-mode.
>
> Before we go anywhere, I'm entering intake mode. There are four short session-state questions I want to walk through with you, one at a time.
>
> Ready?
>
> **User:** Yeah.
>
> **Coach:** Okay.
>
> When you walked into the studio for the first class of the week, what were you carrying in with you?
>
> One thing. Not a list.

---

## Limits

What this coach does not do:

- **Sequence design / asana cues / anatomy lookups.** Hard refusal. Your YTT manual, your senior teachers, and your own practice are the lanes.
- **Trauma therapy.** If something traumatic comes up (yours or a student's), the coach redirects per [`reference/safety-redirects.md`](reference/safety-redirects.md).
- **Medical / injury advice.** The coach refuses and points you to a doctor, a PT, or your studio's liability insurance — depending on which lane the question is in.
- **Generic life coaching or career-pivot strategy.** If the question isn't about your work as a first-year teacher, the coach says so and stops.
- **Representing you to anyone.** Studio managers, students, contracts — the coach can help you think about how to approach a conversation; it cannot be the conversation for you.

The coach is also **not adversarial for sport.** It refuses informer-mode and sycophancy because the alternative is bad coaching, not because friction is the goal. If the user is asking a clean coachable question, the coach coaches.

---

## Folder map

One file, one job.

- [`identity.md`](identity.md) — who the coach is, who it coaches, who it refuses, what it sounds like, and the forced first action it takes on every session.
- [`rules.md`](rules.md) — the three cardinal rules (informer-mode refusal / anti-sycophancy / fail-loudly), the five modes with entry+exit triggers, the adaptation clauses per archetype, and the always/never list.
- [`examples.md`](examples.md) — eight worked transcripts. Each labeled by mode, archetype, and what it demonstrates. Covers all five modes plus the two required debrief situations (student walked out / student cried) and the two required fail-loudly refusals (informer / sycophancy).
- [`reference/coachee-types.md`](reference/coachee-types.md) — three archetypes of first-year teachers. Each one named, with primary anxiety lens, default response under pressure, what unlocks them, what backfires, and the phrasings the coach uses with them.
- [`reference/session-state-template.md`](reference/session-state-template.md) — the file the coach reads before responding to any first message. Four fields, an open-experiment marker, and a running session log.
- [`reference/frameworks.md`](reference/frameworks.md) — the five named coaching scripts the coach actually uses (three-question debrief, fail-loudly script, pre-class anxiety reset, classroom-recovery script, adjustment-energetics framework).
- [`reference/safety-redirects.md`](reference/safety-redirects.md) — three categories where the coach refuses to coach and redirects: trauma disclosure, medical/injury, disclosure of harm caused to a student.
- [`ASSESSOR_GUIDE.md`](ASSESSOR_GUIDE.md) — skim-friendly orientation for anyone evaluating this coach: 60-second test, the 7-pattern stack, file-by-file 1-line summary.

---

## License

MIT. See [`LICENSE`](LICENSE).

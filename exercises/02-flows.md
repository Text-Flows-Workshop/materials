# Exercises 2 — Flows

*Hands-on exercise sheet · ~45 minutes, solo · builds on
[Exercises 1 — Foundations](01-foundations.md).*

> A **text flow** is a repeatable path: text comes from somewhere (a source),
> gets transformed (by you, a tool, or a model), and lands somewhere (a
> destination). Foundations gave you the moves; these four exercises chain
> them into flows you'll actually reuse.

Each exercise: **goal · steps · what you should notice · self-check**.
Everything works with free tools.

---

## Exercise 2.1 — Speech-to-text capture (~10 min)

### 🎯 Goal

Dictate a genuinely messy braindump by voice, then have an LLM structure
it — and discover that the mess is a *feature*, not something to apologize
for.

### Steps

1. Pick a speech-to-text route (free options in every row):
   - The **voice input button** in ChatGPT or Claude (mobile or desktop) —
     zero setup.
   - A dictation app: [MacWhisper](https://goodsnooze.gumroad.com/l/macwhisper)
     (macOS, free tier), [superwhisper](https://superwhisper.com/) (macOS,
     Windows beta), [WhisperTyping](https://whispertyping.com) (Windows).
   - Your OS's built-in dictation (macOS: press the dictation key;
     Windows: **Win + H**).
2. Choose a real topic with loose ends — a project you're behind on, an
   event you're planning, a decision you keep postponing.
3. **Talk for two full minutes without stopping.** Do not compose sentences.
   Ramble, backtrack, contradict yourself, say "oh and also." If you catch
   yourself pre-structuring in your head, speed up.
4. Take the raw transcript and send it to an LLM with a structured prompt:

   ```
   Below is a raw voice braindump. Please:
   1. Organize it into themes with headings.
   2. Extract every action item as a checklist.
   3. List open questions I raised but did not answer.
   4. Flag anything I said that contradicts something else I said.

   """
   <paste transcript here>
   """
   ```

5. Read the output against your memory of what you *meant*.

### 👀 What you should notice

- Two minutes of talking produced far more raw material than two minutes of
  typing would have — including details that "slipped out" precisely because
  you weren't busy summarizing your own cognition.
- The model doesn't mind the mess. Structuring is *its* job in this flow;
  yours was only to get the thoughts out of your head.
- The contradiction-flagging line (step 4.4) often finds something real.
  That's the model as mirror, not oracle: it shows you what you said, and
  *you* judge it.

### ✅ Self-check

Compare the model's structured list against your spoken braindump on two
counts: (1) every specific detail you *named aloud* (a person, a date, a
number) survives into the list, and (2) the list contains **no items you
never said** — models sometimes helpfully invent a plausible task. Either
kind of mismatch is the finding: the technique's value and its failure
modes, both visible in one pass.

---

## Exercise 2.2 — Transcript mining: the decision-log (~12 min)

### 🎯 Goal

Turn a long transcript nobody will ever reread into a compact
**decision-log** — one of the most immediately useful flows for anyone who
sits in meetings.

### Steps

1. Get any transcript. In rough order of convenience:
   - A meeting transcript your videoconferencing tool already generated
     (most major ones now do this).
   - A YouTube video's transcript (on a video page: *…more* →
     *Show transcript*, then select-all and copy — a ragged copy is fine,
     you know how to handle mess now).
   - A recording of your own, transcribed with one of the Exercise 2.1
     apps — modern local transcription handles long recordings, often with
     speaker identification, far faster than listening time (speed depends
     on your hardware, model, and settings).

   ⚠️ Use a transcript you're allowed to process, and mind your
   organization's rules about what may be pasted into which model
   (see the worksheet's *Model Landscape* section).
2. Send it with this structured prompt — note the fences, and note that the
   *shape of the output* is specified before the data appears:

   ```
   Below is a meeting transcript. Produce a DECISION LOG with exactly
   these sections:

   ## Decisions made
   For each: the decision, who made or owns it, and any deadline.

   ## Action items
   A checklist: task — owner — due date (write "unspecified" if absent).

   ## Deferred or unresolved
   Questions raised but explicitly punted, and to when.

   Rules:
   - Only include what is actually in the transcript. Do not infer
     decisions that were merely discussed.
   - Quote the speaker's words for each decision (short quote).

   """
   <paste transcript here>
   """
   ```

3. **Audit one entry.** Pick a single decision from the log and find the
   quoted line in the original transcript. Is it truly a decision, or was it
   just discussion the model upgraded?
4. Tweak the prompt once based on what you found (e.g., tighten the "only
   what is actually in the transcript" rule, or add a section you missed)
   and rerun. Save the winning prompt — it's now a reusable asset.

### 👀 What you should notice

- The short-quote rule is doing heavy lifting: it makes every claim
  **auditable in seconds**. A log you can spot-check is worth ten you have
  to trust.
- "Decisions made" vs. "deferred" is a distinction the transcript's
  participants themselves were probably fuzzy about. Asking for it sharpens
  the meeting after the fact.
- Ask yourself the worksheet's two questions about one entry: *Why is it
  saying this?* and *Do I agree?*

### ✅ Self-check

You verified at least one quoted decision against the raw transcript, and
you saved a prompt you'd genuinely paste into next week's meeting notes. Both,
or it doesn't count.

---

## Exercise 2.3 — The shelf workflow (~10 min)

### 🎯 Goal

Use a **shelf** to gather five items — 3 screenshots + 2 text snippets — for
one support request, *before* writing a word of it. Gathering first, composing
second: that separation is the flow.

### Steps

1. Install a free shelf if you don't have one:
   [Yoink](https://eternalstorms.at/yoink/) (macOS),
   [DropPoint](https://droppoint.netlify.app/) (Windows) or
   [Dropshelf](https://apps.microsoft.com/detail/9mzpc6p14l7n) (Windows).
   *(No shelf available? A folder on your desktop plus your clipboard
   history from Exercise 1.3 is a serviceable stand-in.)*
2. Pick a real (or realistic) tech problem you'd report to a help desk or
   ask a model about — a dialog that won't close, a setting you can't find,
   an error message, a document that renders wrong.
3. **Gather to the shelf, without composing anything yet:**
   - Screenshot 1: the error or problem itself.
   - Screenshot 2: the relevant settings panel or the state just *before*
     the problem.
   - Screenshot 3: version/about info (the About box, or the account/plan
     screen).
   - Text snippet 1: the exact error text, copied as text (not retyped from
     the screenshot — copy the real characters if at all possible).
   - Text snippet 2: one sentence of context in your own words, e.g. "this
     started after Tuesday's update; restarting did not help."
4. Now open a chat with an LLM (or a support-ticket form) and compose in
   one pass, dragging each item off the shelf where it belongs:

   ```
   I need help with the problem shown in the attached screenshots.

   Exact error text:
   """
   <text snippet 1>
   """

   Context:
   """
   <text snippet 2>
   """

   What are the three most likely causes, and what should I check first?
   ```

### 👀 What you should notice

- Gathering and composing are **different mental modes**. Interleaving them
  ("write a sentence… go hunt for the screenshot… where was I?") is where
  support requests become vague. The shelf lets you finish hunting before
  you start writing.
- The exact error text *as text* matters: it's searchable, quotable, and
  the model reads it perfectly — a screenshot of text is a strictly worse
  carrier when you can get the real characters.
- Five artifacts took ~3 minutes to gather and made the request nearly
  answer itself. This is context engineering with your hands.

### ✅ Self-check

All five items sat on the shelf (or in your stand-in folder) **before** you
typed the first word of the request. If you composed as you gathered, run it
once more on a different problem.

---

## Exercise 2.4 — Context engineering: poor vs. curated (~13 min)

### 🎯 Goal

Ask the same question twice — once with lazy context, once with curated
context — and see that the quality of the answer was mostly decided *before
the model ever saw the question*.

### Steps

1. Pick a real question you'd like help with, one that depends on *your*
   situation. Good shapes: "how should I respond to this email?", "how do I
   prioritize these tasks?", "what should I say in this announcement?"
2. **Round 1 — poor context.** In a fresh conversation, ask the question
   with nothing attached:

   > How should I respond to this email from a colleague who is upset about
   > a schedule change?

   Save the answer (clipboard history!).
3. **Round 2 — curated context.** In a *new* conversation, ask the same
   question, but first spend five minutes assembling (shelf or clipboard
   history) and fencing:

   ```
   I need to respond to a colleague upset about a schedule change.

   The email I received:
   """
   <the actual email, or a faithful anonymized version>
   """

   Relevant background:
   """
   - The change was announced <when>, decided by <role — not a name>.
   - What I can and cannot change about the schedule: <one line each>.
   - My relationship with this colleague: <one line>.
   - The outcome I want: <one line>.
   """

   Draft a reply in my voice: direct but warm, under 150 words.
   ```

4. Put the two answers side by side. Mark every sentence in Round 1 that is
   **generic filler** (would apply to anyone's situation) and every sentence
   in Round 2 that is **specific to your facts**.
5. Now look at your background block: which single line changed the answer
   most? Delete it, rerun Round 2 once, and confirm.

### 👀 What you should notice

- Round 1 isn't *wrong* — it's **generic**. The model answered the average
  version of your question, because the average is all it had. This is also
  where "hallucinations" come from: missing context forces the model to fill
  gaps with plausible guesses.
- Round 2's quality came from your five minutes of curation, not from better
  prompting magic. **Context engineering — choosing carefully what to share —
  is the skill.**
- Step 5 teaches the deepest lesson: context items are not equal. Finding
  the load-bearing line (like the train-of-consciousness in the worksheet's
  letter-of-recommendation example) tells you what to gather *first* next
  time.

### ✅ Self-check

You can point at one specific line of context and say "this line is why
Round 2's answer fits my situation and Round 1's doesn't." Not a vibe — a
line.

---

## 🏁 Wrap-up

Four flows, one shape each time: **source → transformation → destination**,
with you curating what enters and judging what exits. Displace effort;
never replace your intentionality.

Next sheet: [Exercises 3 — Advanced](03-advanced.md) — carrying context
*across* models, touching the terminal, and documenting a flow of your own.

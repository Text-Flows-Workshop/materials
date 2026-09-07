# Worked Example Workflows: Before and After

*Companion to the [participant worksheet](../workshop/worksheet.md). Four everyday tasks, each shown twice: the way most of us do it now, and the way it goes once the workshop's tools and habits are in place.*

A recurring theme below, stated once so we don't repeat it four times: in every "after" workflow, the model does the **assembly** — gathering, structuring, formatting, drafting — and you keep the **judgment**. The workshop's maxim is:

> Use LLMs to **displace** effort, not to **replace** your intentionality.

Each "after" ends with a human read-through for exactly that reason. The time saved is real, but it is saved on the mechanical part, not the thinking part.

---

## 1. The Letter of Recommendation

### The task

Dr. Rivera has agreed to write a letter of recommendation for a former student, Sam, who is applying to a master's program. The deadline is Friday. Dr. Rivera knows Sam well — supervised a project, remembers specific moments of initiative — but the letter has been sitting on the to-do list for two weeks, because "write letter" really means "produce two polished pages from a blank screen."

### Before

1. Open a blank document. Stare at it. (10–20 min, mostly spent re-reading old letters for a template.)
2. Dig up Sam's résumé from email; open the transcript in another window; alt-tab between three windows while writing.
3. Draft paragraph by paragraph, constantly interrupted by formatting and phrasing decisions ("is *diligent* too weak? did I already say *impressive*?").
4. Run out of steam halfway; finish it the next day, with a slightly different tone in the second half.

**Honest estimate: 1.5–3 hours of effort, spread over days, most of it friction rather than thought.** The actual *knowledge* — why Sam deserves the letter — was available in the first five minutes.

### After

1. **Gather the data** (5 min): save Sam's transcript and résumé as text. If they arrive as formatted documents, paste them through a formatting cleaner (PastePlainText, Puppypaste) so the model gets clean plain text. Park the pieces on a shelf (Yoink, DropPoint) or in a clipboard manager so they are one drag away.
2. **Dictate the judgment** (5–10 min): open a speech-to-text tool (MacWhisper, superwhisper, or the chat app's voice input) and *talk* about Sam — unstructured, unpolished, exactly as you'd describe them to a colleague in the hallway. The rambling is a feature: details slip out that a typed summary would have compressed away.
3. **Assemble the prompt** (2 min): instructions on top, then each piece of data inside `"""` delimiters — signature, transcript, résumé, transcribed train of consciousness. (The worksheet's Letter of Recommendation section shows the canonical version of this prompt; the variant below adds a recipient-awareness twist.)
4. **Read and own the draft** (10–15 min): the model's letter will be fluent but it may over-praise, flatten a nuance, or state something you *didn't* say. Cut what you don't stand behind. You sign this letter; the model doesn't.

**Honest estimate: 25–35 minutes, in one sitting.**

### What changed and why it matters

The blank page never appears. The "before" workflow forces you to do judgment and assembly *simultaneously* — hold your opinion of Sam in your head while also making paragraph-level formatting decisions. The "after" workflow separates them: judgment is captured cheaply by voice (where it flows naturally), and assembly — the part the model is genuinely good at — is delegated. Note what is **not** delegated: the train of consciousness is the load-bearing input. A model given only the transcript and résumé would produce a plausible letter about nobody in particular.

### The prompt

```
We are going to write a LETTER OF RECOMMENDATION for a former student applying to a MASTERS PROGRAM in data science. The committee reads hundreds of letters; concrete specifics matter more than superlatives.

I am the letter writer; here is my professional signature:
"""
Dr. Alex Rivera
Program Director, Data Sciences
School of Engineering
"""

Here is the candidate's transcript:
"""
<paste transcript here>
"""

Here is the candidate's résumé:
"""
<paste résumé here>
"""

Here is my unedited, spoken train of consciousness about the candidate (transcribed from voice — expect informal phrasing and tangents; the tangents often contain the good details):
"""
<paste transcription here>
"""

Please assemble a letter of about 2 pages (5–6 paragraphs), addressed to "Dear Masters Program Admissions Committee". Ground every claim of strength in a specific detail from my train of consciousness or the documents — do not invent anecdotes or add praise I did not express. Where my spoken notes are ambiguous, flag the sentence with [CHECK] rather than guessing.
```

---

## 2. The Meeting Follow-Up

### The task

You ran a one-hour working-group meeting — say, the committee planning the fall training calendar. Six people, a loose agenda, decisions made verbally, action items scattered through the conversation. Everyone expects a follow-up email with what was decided and who is doing what. You recorded the meeting (with participants' knowledge).

### Before

1. Put off the follow-up for a day or two (the recording is an hour long; re-listening feels like attending the meeting twice).
2. Eventually re-listen — scrubbing back and forth to catch who volunteered for what. (45–75 min.)
3. Type notes as you listen, then reshape the notes into an email. (20–30 min.)
4. Send it three days after the meeting, when half the momentum is gone.

**Honest estimate: 1–2 hours, delayed by days.** The delay is often worse than the time cost: action items assigned Thursday and confirmed the following Tuesday quietly die.

### After

1. **Transcribe locally** (about 30 seconds): a modern local transcription app (MacWhisper or similar) turns the hour of audio into a diarized transcript — speaker-labeled text — in roughly half a minute, on your own machine. Local matters here: the audio never leaves your computer, and only the *text* you choose goes to the model.
2. **Skim and redact** (3–5 min): scan the transcript. Meetings wander — if ten minutes were spent on a sensitive personnel aside, cut those lines before sharing. This is context engineering: you choose what the model sees.
3. **Assemble the prompt** (2 min): instructions, then the agenda and the transcript, each in its own `"""` block. The agenda is the secret ingredient — it gives the model the *intended* structure to reconcile the wandering conversation against.
4. **Verify names and commitments** (5–10 min): diarization mislabels speakers sometimes, and "I could maybe look into that" is not the same as "I'll do it." Check every (owner, action, deadline) triple against your memory of the room before sending. Then send — same afternoon.

**Honest estimate: 15–20 minutes, same day.**

### What changed and why it matters

Audio became text, and text is the interface. An hour of audio is opaque — you can only re-experience it in real time. The same hour as a transcript is searchable, quotable, excerptable, and shareable-in-part. Once the meeting is text, synthesis is an assembly job. The judgment you keep: what was *actually* agreed to (models are eager to promote tentative musings into action items), and what was too sensitive to paste in the first place.

### The prompt

```
Below are the agenda and the diarized transcript of a one-hour planning meeting I ran today. Speaker labels come from automatic diarization and may occasionally be wrong.

Here is the agenda we intended to follow:
"""
<paste agenda here>
"""

Here is the transcript:
"""
<paste transcript here>
"""

Please produce:

1. DECISIONS — a bulleted list of decisions actually made (not options merely discussed). For each, quote the sentence from the transcript that records the decision.
2. ACTION ITEMS — a table: owner, action, deadline. Include only items someone clearly committed to; put tentative or unassigned items in a separate "Unowned / tentative" list.
3. OPEN QUESTIONS — anything raised but not resolved.
4. DRAFT EMAIL — a short, friendly follow-up email to the group (subject line included) summarizing 1–3. Plain tone, no corporate filler.

If the transcript contradicts the agenda (items skipped, added, or reordered), note that briefly at the top.
```

---

## 3. Turning a Document into a Presentation

### The task

You wrote the Q3 report — twelve pages on program enrollment, budget, and next-quarter plans. Now the steering committee wants "a short deck" of it for Thursday. Same content, different medium.

### Before

1. Open the report and a blank slide deck side by side.
2. For each section: select text, copy, paste into a slide, watch the formatting explode (wrong fonts, ghost styles), fix it by hand, trim the paragraph into bullets. Repeat ~15 times. (60–90 min.)
3. Realize slide 9 duplicates slide 4 because the report said the thing twice; restructure. (15 min.)
4. Fight the slide tool's outline view for the conclusion. Give up and screenshot a table from the report; it's now an unreadable image.

**Honest estimate: 1.5–2.5 hours, most of it fighting a WYSIWYG tool** — and the deck's *structure* is an afterthought, inherited from the report rather than designed for a live audience.

### After

1. **Get the report into plain text** (2–5 min): export or paste the report as Markdown (a formatting cleaner helps if it comes out of a word processor with styling debris). Models are far more comfortable with plain-text source than with anything WYSIWYG — this is the workshop's compositional-tools principle in action.
2. **Ask for a restructuring, not a compression** (1 min): the prompt below asks the model to *re-architect* the content for a listening audience — slides are a different rhetorical form, not a shorter report.
3. **Import** (2 min): paste the slide-formatted Markdown into a Markdown-importable slide tool (e.g. slides.com's Markdown import, or any Markdown-slides tool your unit uses). Structure arrives intact; no per-slide copy-paste.
4. **Rehearse against it** (15–20 min): the model doesn't know which finding the committee will push back on, which number is politically delicate, or what you want the room to remember. Reorder for *your* emphasis, cut slides you can say in a sentence, and check every number against the report — restructuring is where transcription errors sneak in.

**Honest estimate: 25–35 minutes to a working deck.**

### What changed and why it matters

You stopped moving *formatting* between tools and started moving *text*. The before-workflow's cost is almost entirely the impedance mismatch between two WYSIWYG surfaces; plain text (Markdown) passes through the model and into the slide tool without friction, because every tool in the chain speaks it. The deeper win: because restructuring became cheap, you can afford to ask for the deck to be *designed as a deck* — a narrative for listeners — instead of settling for the report's structure with fewer words. The judgment you keep is emphasis: what Thursday's room actually needs to hear.

### The prompt

```
I need to turn a written report into a slide presentation. Do not simply compress the report: restructure it for a live audience that will HEAR it, with one idea per slide.

Constraints:
- Output pure Markdown formatted for a Markdown-slides tool: "# " starts a new slide with a title; "---" on its own line separates slides.
- At most 12 slides. At most 4 bullets per slide, each under 12 words.
- Slide 1: title slide. Slide 2: the single most important takeaway, stated plainly. Last slide: decisions we are asking the committee to make.
- Keep tables as Markdown tables, trimmed to only the rows/columns that support the point of that slide.
- Do not invent numbers, projections, or claims not present in the report. If a slide needs a figure the report doesn't contain, insert the placeholder [NEEDED: description].
- After the slides, add a section "CUT FROM THE REPORT" listing the report content you left out, one line each, so I can check nothing essential was dropped.

Here is the report, in Markdown:
"""
<paste Q3 report here>
"""
```

---

## 4. The Support Request with Visual Context

### The task

The grant-budgeting software keeps rejecting a form: an error appears, the save button greys out, and it worked fine last month. You need help from IT support — or from an LLM directly — but the problem is intrinsically *visual*: it lives in a dialog box, a greyed-out button, a red banner.

### Before

1. Write an email: "The budget module gives an error when I try to save. It says something about validation. Can you help?" (10 min.)
2. Reply, next day: "Which screen? What's the exact error? Can you send a screenshot?"
3. Take one screenshot, forget the other screen, paraphrase the error from memory (incorrectly).
4. Two more round-trips to establish what you could have shown on day one.

**Honest estimate: 30–45 minutes of your writing time — spread across 3–5 exchanges over several days.** The cost isn't the minutes; it's the latency, and the fact that each exchange transmits a lossy *description* of the screen instead of the screen.

### After

1. **Collect while you reproduce** (5 min): walk through the failing steps once more with a shelf open (Yoink, DropPoint, Dropshelf). Screenshot each state — the filled form, the error dialog, the greyed-out button — and drag each shot onto the shelf as you go. The shelf holds the pile so you don't juggle windows.
2. **Capture the error as text** (1 min): wherever the error message is selectable, copy it and paste it through a plain-text cleaner. Exact error text is searchable and precise; "something about validation" is neither. Before anything leaves your machine, glance over shots and text for sensitive data (account numbers, personal names) and crop or redact.
3. **Send one complete request** (3 min): attach the screenshots from the shelf and paste the delimiter-structured request below. Everything the other side would have asked for across three round-trips arrives in message one. The same package works whether the recipient is IT support or a vision-capable LLM you ask first.
4. **Evaluate the answer** (varies): a model's diagnosis is a hypothesis, not a verdict — it can't see your permissions, your version, or your data. Try the suggested fix on a low-stakes case first; don't run destructive steps ("clear the cache", "delete the draft") on the only copy of real work.

**Honest estimate: about 10 minutes to send a request that usually resolves in one exchange.**

### What changed and why it matters

Context moved from *described* to *shown*, and from *scattered* to *assembled*. Every "before" round-trip existed to recover information you had on your screen the first day. The shelf makes gathering visual evidence nearly free, and the `"""` structure separates the three things a helper needs — what you expected, what happened, what it said exactly — so nothing has to be asked for twice. This is context engineering at its most literal: the quality of the help you get is a function of the context you package. The judgment you keep: what's safe to share, and whether the proposed fix is safe to try.

### The prompt

```
I need help with a problem in our grant-budgeting software. I've attached screenshots of each step; the exact error text is pasted below.

What I was trying to do:
"""
Submit the Q3 budget revision form for an active grant. This exact workflow succeeded last month.
"""

What happened, step by step (matching the attached screenshots in order):
1. Filled in the revision form (screenshot 1).
2. Clicked "Validate" — a red banner appeared (screenshot 2).
3. The "Save" button became greyed out and stayed greyed out (screenshot 3).

The exact error text, copied from the banner:
"""
Validation failed: allocation total (104.2%) exceeds permitted maximum for category B. Contact your administrator if you believe this is an error. [ERR-BDG-0417]
"""

What I've already tried:
"""
Logged out and back in; tried a different browser; re-entered the category B amounts by hand. Same error each time.
"""

Please: (1) explain what this error most likely means in plain terms, (2) list the most likely causes in order of probability, and (3) for each cause, tell me what to check or try — flagging any step that could lose data or change the form so I can make a backup first.
```

---

## The pattern across all four

| | Before | After |
|---|---|---|
| Where your time goes | Assembly *and* judgment, tangled together | Judgment only; assembly is displaced |
| Shape of the input | Whatever's at hand, described from memory | Deliberately gathered plain text + `"""` structure |
| Number of passes | Many small frustrated ones | One gathering pass, one drafting pass, one **human review pass** |
| What the model gets | An underspecified request | Engineered context: instructions separated from data |
| What you keep | (everything, exhaustedly) | The opinion, the emphasis, the verification, the signature |

The review pass is not optional overhead — it *is* the workflow. In each example the model's output needed a human catch: the letter that over-praises, the "action item" nobody committed to, the restructured number that drifted, the fix that would delete a draft. Displace the effort; never the intentionality.

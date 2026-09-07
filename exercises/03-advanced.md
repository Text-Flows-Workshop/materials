# Exercises 3 — Advanced

*Hands-on exercise sheet · ~45 minutes · best in pairs, works solo · builds
on [Exercises 1](01-foundations.md) and [Exercises 2](02-flows.md).*

> By now you move text deliberately and you engineer context on purpose.
> This sheet pushes into the places where those skills compound: across
> *models*, through the *terminal*, and finally into a flow **you** design
> and write down so a colleague could run it.

If you're in pairs: one person drives, the other reads the "what you should
notice" section aloud afterward and challenges the self-check. Swap each
exercise. Everything works with free tools.

---

## Exercise 3.1 — Agent-hopping (~12 min)

### 🎯 Goal

Carry one conversation from model A to model B through your clipboard, and
find out precisely **what context survives a hop — and what silently
doesn't**.

### Steps

1. Open a conversation with model A (any free chat: ChatGPT, Claude,
   Gemini…). Have a short but *stateful* exchange — 4–6 turns where the
   model learns things about your task. Good seed: plan a small event, and
   over the turns tell it the date, the headcount, a constraint, and one
   decision you made together ("we settled on option 2").
2. Ask model A one more question and note the answer quality — it has full
   context.
3. Now **hop**. Select the entire conversation, copy it, and open model B
   (a *different* vendor's chat). Paste it fenced, with a handoff header:

   ```
   You are taking over a conversation I was having with another AI
   assistant. The full transcript is below. Read it, then continue
   helping me from where it left off. Before we continue, list:
   1. What you understand my goal to be.
   2. Every constraint and decision established so far.

   """
   <paste the whole conversation>
   """
   ```

4. Compare model B's list against what actually happened in conversation A.
   What did it get? What's missing?
5. Now hunt for what the **clipboard itself** dropped: things model A knew
   that were never *in the visible text* — attached files, images, its
   memory of your earlier chats, custom instructions you've set. None of
   those crossed the hop. Also check the paste for mangling — as you know
   from Foundations, formatting and links may have been transformed.

### 👀 What you should notice

- The visible transcript hops beautifully; the **invisible context**
  (attachments, per-account memory, system-side instructions) doesn't hop
  at all. What survives is exactly *what made it into plain text* — a very
  concrete restatement of the workshop thesis.
- The "before we continue, list…" read-back is the professional move: it
  converts a silent context loss into a visible, fixable one. Use it any
  time you hand context over — to a model *or* a colleague.
- You are not locked into one vendor. A conversation kept in text is
  portable; this is a quiet but real form of independence.

### ✅ Self-check

You can name at least **two** things model A knew that model B provably
didn't after the hop, and say for each whether the fix is "paste more text"
or "can't cross in text at all."

---

## Exercise 3.2 — Terminal one-liners (~10 min)

### 🎯 Goal

Touch the clipboard from the command line — once — and see that the terminal
is just another station your text flows through, not a members-only club.

*(Never used a terminal? Perfect — this is a 3-command exercise. macOS: open
**Terminal**. Windows: open **PowerShell**. Type each line, press Enter.)*

### Steps

1. Copy a few paragraphs of any text (an email, a page section — something
   with a handful of lines).
2. **Look at your clipboard from the terminal:**
   - macOS: `pbpaste`
   - Windows: `Get-Clipboard`
   - Linux: `xclip -o` (or `wl-paste`)

   Your clipboard's plain-text contents print right there. Same clipboard,
   new window into it.
3. **Pipe it through a tool.** The `|` character means "send the output of
   the left command into the right command":
   - macOS/Linux: `pbpaste | wc -w` — word count of your clipboard.
   - Windows: `(Get-Clipboard | Measure-Object -Word).Words`
4. One more, on a *list*: copy a handful of lines (names, tasks, anything,
   one per line), then sort your clipboard alphabetically:
   - macOS/Linux: `pbpaste | sort`
   - Windows: `Get-Clipboard | Sort-Object`

   Bonus (macOS/Linux): round-trip it — `pbpaste | sort | pbcopy` — and
   paste anywhere: your clipboard now *contains* the sorted list.
5. Where this road leads (optional, for later): CLI chat tools like
   [Chatblade](https://github.com/npiv/chatblade) accept piped text — so
   `pbpaste | chatblade summarize this` sends your clipboard to a model
   without a browser. Agentic terminal clients (`claude-code`, `codex`) and
   AI-native IDEs live one step further down the same road.

### 👀 What you should notice

- `pbpaste` / `Get-Clipboard` demystify the clipboard: it's not a place
  inside one app, it's a system-wide text slot **any** tool can read.
- The pipe `|` is the terminal's native text flow — source → transformation
  → destination, the exact shape from Exercises 2, in one line of text.
- You didn't need to be a programmer. Terminal tools take plain text in and
  put plain text out, which is precisely why they compose so well with
  everything else in this workshop.

### ✅ Self-check

You ran at least one pipeline containing a `|`, and you can explain to your
pair partner (or a rubber duck) what flowed from where to where.

---

## Exercise 3.3 — The Executive TL;DR drill (~8 min)

### 🎯 Goal

Run the 2-minute "Managing Up with AI" drill against a real email chain —
under time pressure, because the time pressure *is* the exercise.

### Steps

1. Open the **prompt scaffold** in the facilitation guide:
   [`../workshop/facilitation.md`](../workshop/facilitation.md), section
   *"Bonus: the 2-Minute Mini-Drill"*. Copy the scaffold from there — we
   won't duplicate it here; the guide's copy is the canonical one.
2. Find yesterday's (or this week's) **longest email chain**. The uglier
   the better.
3. Set a visible 2-minute timer. Go:
   - Paste the chain under the scaffold (fenced — you know the drill).
   - Fill the scaffold's blanks: context, ask, decision deadline.
   - Send; read the draft; fix tone and any factual slip.
4. Timer done? Now the payload step, exactly as the guide prescribes:
   answer — in pairs if you have one, in writing if solo —
   **"what did the AI miss?"** Name at least one thing: a nuance of
   politics, a stale fact deep in the chain, an implied risk, a
   relationship you know about and the transcript doesn't.

### 👀 What you should notice

- Two minutes is genuinely enough for a serviceable executive brief — once
  the scaffold exists. The scaffold is a **saved, worked-on prompt**: the
  asset you were told in Foundations to start collecting.
- Step 4 is not a debrief formality; it's the division of labor made
  visible. The model produced the first draft; the miss-list is *your
  judgment*, and it's the part with your name on it.

### ✅ Self-check

You have a sendable brief **and** a named miss. If your miss-list is empty,
you haven't read the draft as its accountable author yet — read it once more
asking "what would embarrass me if I sent this as-is?"

---

## Exercise 3.4 — Capstone: build (and document) your own flow (~15 min)

### 🎯 Goal

Take one recurring task from your own work and turn it into a **named,
documented text flow** — written down well enough that a colleague could run
it without you in the room. This is the workshop paying rent in your real
job.

### Steps

1. **Pick the task.** Recurring, text-heavy, mildly annoying. Signs of a
   good candidate: you do it weekly or more; it involves copying from one
   place to another; you always structure the output the same way. (Weekly
   status notes, triaging a shared inbox, prepping agendas, summarizing
   tickets, tidying meeting notes…)
2. **Name it.** A flow with a name becomes a *thing* you can improve, share,
   and talk about: "the Monday digest flow," "the intake triage flow."
3. **Draw the pipeline** in one line, using the shape from Exercises 2:

   ```
   SOURCE(S)  →  TRANSFORMATION(S)  →  DESTINATION
   e.g.: 6 status emails  →  paste fenced into saved prompt; model merges
   into themed digest; I audit owners & dates  →  Monday note to my team
   ```

   Be honest about the human steps — the audit *is* part of the flow.
4. **Write the prompt** at the flow's heart, in full instructions-`"""`data
   form, and run the flow once end-to-end on real (or realistic) material.
   Fix what breaks; save the prompt.
5. **Document it in the 8-column schema** from the facilitation guide
   ([`../workshop/facilitation.md`](../workshop/facilitation.md), the
   *Spreadsheet Cleanup* table in step 5): one row — Summary, Category,
   Popularity, Example Prompts, Data Required, Models Tested, Effectiveness,
   Notes. That schema exists precisely so individual discoveries become
   organizational knowledge; your flow is now in the interchange format.
6. **In pairs**: swap rows. Each partner tries to run the *other's* flow
   from the row alone, no questions allowed for the first three minutes.
   Every question they eventually ask is a missing cell — patch the row.
   *(Solo: leave the row overnight, then run your own flow tomorrow using
   only what you wrote.)*

### 👀 What you should notice

- The hard part wasn't the prompt — it was **naming the sources and the
  human checkpoints**. Most "AI didn't work for me" stories are actually
  undocumented-flow stories.
- The pair test (or overnight test) is the honesty mechanism: a flow that
  lives only in your head isn't a flow yet, it's a habit. Written in plain
  text, it's something colleagues can pick up and **combine into their own
  flows** — the release ethic that animates all of these materials.

### ✅ Self-check

One row, all eight columns filled, prompt saved, flow run end-to-end at
least once — and one other person (or tomorrow-you) executed it without
asking you anything a cell should have answered.

---

## 🏁 Wrap-up — and what's next

You've hopped context across vendors, piped your clipboard through a
terminal, briefed an executive in two minutes, and shipped one documented
flow of your own.

The durable habit is the last one: **when you discover a flow, write it
down in plain text and pass it on.** One row per discovery. That's how a
room full of individual experiments becomes an organization that knows what
it knows.

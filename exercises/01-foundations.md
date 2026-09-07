# Exercises 1 — Foundations

*Hands-on exercise sheet · ~30 minutes, solo · no programming required.*

> Text is not just a medium — it's the **interface** for cognition with LLMs.
> These four exercises build the muscle memory that everything else rests on:
> seeing what text *actually is* under the formatting, and moving it around
> deliberately.

Work through them in order. Each one has a **goal**, **steps**, a **"what you
should notice"** section (read it *after* trying, not before), and a
**self-check** so you know you're done.

Everything here works with free tools.

---

## Exercise 1.1 — Rich text vs. plain text (~5 min)

### 🎯 Goal

See with your own eyes that every formatted document is *two* things at once —
the text, and the formatting wrapped around it — and that a copy-paste can
carry either one.

### Steps

1. Open any richly formatted page: a Wikipedia article works well (headings,
   links, bold, a table if you can find one).
2. Select a few paragraphs **including a heading and at least one link**, and
   copy them.
3. Paste them into a rich-text destination: an email draft, Google Docs, or
   Word. Look at what arrived.
4. Now paste the *same clipboard* into a plain-text destination: the address
   bar of your browser (don't hit Enter!), Notepad (Windows), or TextEdit
   after choosing *Format → Make Plain Text* (macOS).
5. Compare the two pastes side by side. In most apps you can also force a
   plain paste directly: **Ctrl+Shift+V** (Windows/Linux) or
   **Cmd+Shift+V** / *Paste and Match Style* (macOS). Try it.

### 👀 What you should notice

- The rich paste kept headings, bold, and links; the plain paste kept only
  the characters. The link *text* survived — the link *destination*
  (the URL) vanished.
- Formatting is **information**: section structure tells a reader (or a
  model) what's a title and what's a body; a link carries a URL you can no
  longer recover from the plain version.
- Neither version is "correct." The skill is knowing **which one you're
  holding** and which one your destination needs.

### ✅ Self-check

You can answer, without looking: *when I paste this clipboard into a chat
window, will the model see the URLs or not?* If you hesitate, paste into a
plain-text destination once more and look.

---

## Exercise 1.2 — The delimiter pattern (~8 min)

### 🎯 Goal

Rewrite a real, messy prompt into the **instructions-then-data** form using
`"""` delimiters — the single highest-leverage habit in prompt craft.

### Steps

1. Find a real prompt you (or a colleague) actually sent to an LLM where
   instructions and pasted material were mixed together in one blob. If you
   don't have one handy, use this deliberately messy specimen:

   > can you make this email nicer Hi team the deadline moved to Friday
   > because vendor delays also please remind everyone about the badge
   > renewal thing thanks — also keep it short and professional and don't
   > mention the vendor by name

2. Separate it into three parts on paper or in a scratch file: **the task**,
   **the constraints**, **the data** (the raw email text).
3. Rewrite it in this shape:

   ```
   Rewrite the email below so it is short and professional.

   Constraints:
   - Do not mention the vendor by name.
   - Keep the Friday deadline and the badge-renewal reminder.

   Here is the email:
   """
   Hi team the deadline moved to Friday because vendor delays also
   please remind everyone about the badge renewal thing thanks
   """
   ```

4. Send **both** versions — the messy original and your rewrite — to the same
   model, in two separate conversations. Compare the answers.
5. Save your rewritten prompt somewhere you'll find it again. Worked-on
   prompts are assets, not scratch paper.

### 👀 What you should notice

- In the messy version, the model has to *guess* where your instructions end
  and your data begins — and sometimes "fixes" your instructions as if they
  were part of the email.
- With `"""` fences, that ambiguity disappears. The model treats the fenced
  block as material to work *on*, not instructions to work *from*.
- Constraints pulled out as a list get followed more reliably than
  constraints buried mid-sentence.

### ✅ Self-check

Look at your rewrite: could a stranger tell, at a glance and without reading
carefully, which lines are *your voice* and which lines are *pasted
material*? If yes, the pattern is doing its job.

---

## Exercise 1.3 — Clipboard history (~10 min)

### 🎯 Goal

Set up a clipboard manager, then feel the difference on a task that needs
**three snippets at once** — the moment a single-slot clipboard stops being
enough.

### Steps

1. **Set up clipboard history** (one-time, free):
   - **Windows**: press **Win + V**. If it's off, one click enables it
     (Settings → System → Clipboard). Done.
   - **macOS**: install a free clipboard manager — for example
     [Maccy](https://maccy.app) (free, open source) — or use one you already
     have, such as [Keyboard Maestro](https://www.keyboardmaestro.com/main/)'s
     clipboard history if you own it.
   - **Linux**: your desktop environment likely ships one (e.g.
     GNOME/KDE clipboard applets).
2. **The 3-snippet composition task.** You will draft one message that needs
   three ingredients from three places:
   - **Snippet A**: copy one sentence from any web page (a fact, a policy
     line, a definition).
   - **Snippet B**: copy a sentence from an email or document of yours.
   - **Snippet C**: copy a URL from your browser's address bar.
3. Copy A, then B, then C — **without pasting in between**. Your old
   clipboard would now hold only C.
4. Open a blank draft (email, doc, or chat box) and compose a short
   paragraph that uses all three, pasting each from your clipboard history
   (Win+V picker, or your manager's popup) in the order *B, then A, then C*.
5. Notice you never went back to re-copy anything.

### 👀 What you should notice

- The default clipboard holds **one** item; every copy silently destroys the
  last. Clipboard history turns copy-paste from a relay race into a
  **shelf of parts** you assemble from.
- Composing prompts for LLMs is exactly this kind of assembly: instructions
  snippet + data snippet + context snippet. This is why clipboard history is
  foundation-level, not a power-user luxury.

### ✅ Self-check

You can copy three things in a row and paste them back **in a different
order** without re-copying. If you had to go back to a source page even
once, run the drill again.

---

## Exercise 1.4 — Paste-to-Markdown with Puppypaste (~7 min)

### 🎯 Goal

Use [Puppypaste](https://puppypaste.com) (online, free) to convert a rich
copy into **Markdown** — the format that keeps the *meaning* of the
formatting (structure, links) while staying pure plain text.

### Steps

1. Return to the formatted page from Exercise 1.1 (or any page with
   headings, bold, and links). Copy a section of it.
2. Open [puppypaste.com](https://puppypaste.com) and paste.
3. Look at the Markdown it produces: `#` for headings, `**bold**`,
   `[link text](url)` for links.
4. Copy the Markdown output and paste it into a chat with an LLM, below a
   short instruction such as:

   ```
   Summarize the section below in three bullet points, and list every
   link it contains.

   """
   <paste the Markdown here>
   """
   ```

5. Check the model's answer against the original page: did it get the
   section structure right? Did it recover the links?

*(macOS bonus: [PastePlainText](https://apps.apple.com/us/app/paste-plain-text/id1528231008?mt=12)
(free) does stripping-only, system-wide — handy when you want plain text
without visiting a website.)*

### 👀 What you should notice

- Markdown is the best of both worlds from Exercise 1.1: it is plain text a
  model reads comfortably, **and** it preserves the headings and URLs that a
  naive plain paste destroyed.
- The model could list the links *only because* Markdown carried them.
  Feed it the plain version from Exercise 1.1 and it can't — try it.
- This is why the workshop keeps saying: **prefer Markdown**. It's the
  interchange format of human-LLM text flows.

### ✅ Self-check

You can name, for one concrete page, what each of the three paste forms
preserves: rich paste (looks), plain paste (characters only), Markdown paste
(structure + links, in plain text). Say it out loud — if it takes more than
three sentences, revisit 1.1 and 1.4.

---

## 🏁 Wrap-up

You now control the three states of copied text (rich / plain / Markdown),
you fence data away from instructions with `"""`, and your clipboard holds
more than one thing. That *is* the foundation.

Next sheet: [Exercises 2 — Flows](02-flows.md), where these mechanics
combine into end-to-end workflows: voice in, structure out, context
engineered on purpose.

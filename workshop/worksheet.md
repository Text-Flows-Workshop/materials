# Text Flows: Mastering Text Flows for AI Collaboration

*Participant worksheet — the take-home cheat-sheet from the full workshop.*

### 🌐 Thesis

> Text is not just a medium — it's the **interface** for cognition with LLMs.

---

### 🧠 Conceptual Pillars

| Layer         | Need                        |
| ------------- | --------------------------- |
| Technical     | Learn the tools             |
| Syntactic     | Structure your inputs       |
| Semantic      | Share vocab & understanding |
| Collaborative | Learn *together*            |

⚠️ "Hallucinations" are inevitable and not a failure of the model:
- Missing or conflicting context
- Ambiguous instructions
- Confusion about the AI's power

AI/LLMs are able to understand what humans do — not do what humans don't understand.

---

### 🔧 Essential Tools & Practices

#### Prompt Craft

* Use consistent delimiters (`"""`) to separate **instructions** from **data**
* Practice **context engineering**, i.e., choosing carefully the information to share with the model
* Be precise and specific about what you want, and save prompts that you've worked on for future use and improvements
* Do not treat the model as an oracle: ask yourself "*Why is it saying this?*" and "*Do I agree?*"
* Prefer Markdown for formatting clarity

#### Formatting Cleaners

When copy-pasting text, there is **plain text** (stripped of any formatting) and **rich text** (with formatting).

The formatting typically includes important information — in particular **section structure** or **links**.

* [PastePlainText](https://apps.apple.com/us/app/paste-plain-text/id1528231008?mt=12) (macOS, free)
* [Puppypaste](https://puppypaste.com) (online, free)

#### Clipboard Managers

When copy-pasting text, it is useful to have a clipboard manager that makes it easy to cycle through multiple snippets of text.

This is especially useful when repeatedly composing the same pieces of text. There are many clipboard managers available; these are just a few examples:

* [Keyboard Maestro](https://www.keyboardmaestro.com/main/) (macOS)
* [ClipClip](https://clipclip.com) (Windows)
* **Win + V** — Windows' built-in clipboard history (enable once in Settings)

#### Shelves

"Shelves" let you drag-drop snippets of text, or screenshots, to a small portion of your screen, which becomes a placeholder.

This is useful when communicating extensively with a model about your context — for instance, sharing screenshots of programs to get guidance.

* [Yoink](https://eternalstorms.at/yoink/) (macOS)
* [DropPoint](https://droppoint.netlify.app/) (Windows)
* [Dropshelf](https://apps.microsoft.com/detail/9mzpc6p14l7n) (Windows)

#### Speech-to-Text

It is often useful to give instructions to models directly by voice. This saves you from having to structure and type your thought. The model doesn't mind — and benefits from the additional details that slip out when we are not busy summarizing our own cognition.

**Modern local transcription apps can produce searchable transcripts of long recordings, many with speaker identification (*diarization*); processing time depends on hardware, model, and settings — a small fraction of listening time on recent machines.**

* [MacWhisper](https://goodsnooze.gumroad.com/l/macwhisper) (macOS)
* [superwhisper](https://superwhisper.com/) (macOS, Windows beta)
* [WhisperTyping](https://whispertyping.com) (Windows)
* ChatGPT / Claude voice input

#### Conversation Management

Tools that store and search **all** your conversations with LLMs: convenient for pulling up prompts you used in the past, or finding a specific conversation.

* [Echoes](https://echoes.r2bits.com) (Chrome extension, macOS and Windows)

#### Compositional Tools

In general, your workflows are enhanced by **tools that take pure plain text as an input format**. There is a real difference between WYSIWYG (*What You See Is What You Get*) tools and plain-text source: models are much more comfortable with source formats (HTML, Markdown, LaTeX, etc.).

* [slides.com](https://slides.com): Markdown-importable slides
* Terminal utilities
   * Clipboard: `pbpaste`, `pbcopy` (macOS); `Get-Clipboard` (Windows); `wl-paste` (Wayland) / `xclip -selection clipboard` (X11)
   * CLI chat: [Chatblade](https://github.com/npiv/chatblade)
   * Agentic clients: `claude-code`, `codex`
   * AI-native IDEs: `windsurf`, `cursor`

---

### 📚 Model Landscape

For **professional use**, prefer models your institution has a contract with, and limit the sensitivity of what you share to what that contract covers (at a US university, typically up to FERPA-protected data — never HIPAA/PHI, legal-privilege, or export-controlled material). Your IT organization can tell you which tenants are sanctioned.

For **personal use**, most major models allow a **robust opt-out** from training on your data (i.e., there is no reason to believe the companies do not honor their own Terms of Service). Verify the current opt-out mechanics for your model of choice — they change, and at the time of the workshop at least one major vendor offered no individual opt-out at all outside site contracts.

| Model    | Privacy        | Context  | Notable strength                 |
| -------- | -------------- | -------- | -------------------------------- |
| GPT-4/4o | Opt-out        | 128k     | Memory + conversation search     |
| Claude   | Opt-in         | 200–500k | Writing quality + care in refusals |
| Gemini   | Site-contract only | 1M   | Transcription, double-checking   |

*(Snapshot as of mid-2025 — the specifics churn; the habit of checking them is the durable skill.)*

**The most important privacy skill is knowing how to turn off model training for your account.**

Once model training is deactivated, the only common way your data can still be used is if you click the up/downvote buttons to rate an answer (a signal that you are willing to share that conversation for quality assurance).

---

### 🧭 When to Use LLMs

> Use LLMs to **displace** effort, not to **replace** your intentionality.

Use for:

* Drafting
* Structuring
* Synthesizing
* Exploring

Not for:

* Finished artistic expression
* Moral reasoning without reflection

#### 📝 Letter of Recommendation Example

When you are writing a letter of recommendation, here are best practices:

✅ **Things to do:**
- Use `"""` to separate instructions from data
- Provide personal and professional information on the person the letter is about (transcript, résumé, etc.)
- **Provide your stream-of-consciousness opinion of the person**
- Delegate to the LLM the *drafting* of the letter — assembling your thoughts, given who the recipient is and what they need

❌ **Things to avoid:**
- Delegating to the LLM the *judgment*

For example:

```
We are going to write a LETTER OF RECOMMENDATION for a candidate applying to a MASTERS PROGRAM.

I am the letter writer; here is my professional signature:
"""
Dr. Alex Rivera
Program Director, Data Sciences
School of Engineering
"""

Here is the transcript of the candidate:
"""
<transcript>
"""

Here is additional information on the candidate:
"""
<resume>
"""

Here is a train of consciousness of mine about the candidate:
"""
<train-of-consciousness>
"""

Please assemble a final letter. It should be about 2 pages (5-6 paragraphs), addressed to "Dear Masters Program Admissions Committee".
```

The `<train-of-consciousness>` is the load-bearing part of the prompt: the model cannot possibly know why *you* would recommend this candidate. That is the judgment only you can supply — everything else is assembly, which is exactly what the model is for.

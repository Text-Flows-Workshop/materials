# Text Flows: Working Smarter with AI

*Prompts, Tools, and Real Use Cases from Staff*

A hands-on workshop for university staff — lecture edition (plain-text release).

*July 2025*

---

## Welcome

**"Text Flows"**

- Program:
  - Lecture on Text Flows
  - Activity adapted from an assignment in an undergraduate course
- Why is (collective) AI literacy important?
- **Breaking silos!**

## What is Generative AI?

**"It's Like Having a Really Eager Intern Who..."**

- ✅ Never gets tired
- ✅ Knows a little about everything
- ✅ Loves to help brainstorm
- ❌ Sometimes makes stuff up
- ❌ Needs your expertise to be useful

## Common AI Myths vs Reality

- ❌ **Myth:** "AI will replace me"
  ✅ **Reality:** AI amplifies your expertise
- ❌ **Myth:** "I need to be technical"
  ✅ **Reality:** You just need to know your job
- ❌ **Myth:** "AI is always right"
  ✅ **Reality:** AI needs your judgment

## A "Normal-Technology" Adoption Curve

### Why AI Looks Explosive — but Follows a Familiar S-Shape

> Electricity → Telephony → Internet → *AI*

- Early demos & scare stories → uneven diffusion → eventual ubiquity
- Real leverage comes from *process tweaks at scale*, not moon-shots
- Reading tomorrow's headlines? ✘
  Reading yesterday's adoption patterns? ✔

**WE ARE ONLY AT THE (VERY) BEGINNING OF THE CURVE**

## Why Should Staff Care?

**"Because AI is Coming to Your Desk"**

- A majority of students (surveys report ~59%) already use AI daily
- Your expertise + AI tools = superpowers
- YOU know what actually needs fixing
- YOU understand the human side
- This is not *another tool*, this is **THE** tool

## TEXT RULES!

### Mastering Text Flows for AI Collaboration

- Large **Language** Models are **the future of cognition**
- The **dominant interface** to these powerful systems **is text**
- There are several needs:
  - **technical** ⇨ *you need to learn tools*
  - **syntactic** ⇨ *you need to understand structure*
  - **semantic** ⇨ *you need to develop a shared vocabulary, understanding and cognition*
- and also...
  - **collaborative** ⇨ *none of these tools reach their full potential if we are not all using them knowingly*

## The Cavalry is Arriving

- Better modes of operation are arriving:
  - **Anthropic's Model Context Protocol (MCP):** the USB-C connector of models
  - **Google's Agent2Agent (A2A):** a standard of intercommunication among models, allowing composition of models
- **Much better integrated platforms are coming**
  - But they might take 5–10 years
- In the meantime we must all learn to integrate ourselves

## We Are at the Cusp of a New Platform Shift

- You are entering this world **at an exceptionally exciting time**, but one that will require flexibility and adaptability
- This world will require you to **think responsibly about where we are headed**

## Why "Text Rules" Now?

- LLMs are fundamentally text processors (input text, output text)
  - Multimodal exists, but unstandardized
  - Multimodal exists, but **hard to compose**
- Their power is unlocked by the *quality* and *structure* of the text we provide
- We're moving from simple queries to complex collaborations, requiring assembly of diverse text sources
- Mastering text flow = supercharging your AI interactions

## The Untapped Potential: Text is Everywhere!

- Meeting transcripts (Zoom, Teams, etc.)
- Lecture transcripts
- Voice memos on your phone (now often auto-transcribed!)
- Emails and documents
- Notes (digital or even scanned handwritten)
- Slide content
- Code and logs
- Web clippings

## The Model Landscape (mid-2025 snapshot)

| | **OpenAI (ChatGPT)** | **Anthropic (Claude)** | **Google (Gemini / NotebookLM)** |
|---|---|---|---|
| Reasoning models | o1, o3, o4 | Sonnet 3.7 *ext. thinking* | 2.5 Pro, 2.5 Flash |
| Other models | 4o, 4.5 | Opus 3.0, Haiku 3.5, Sonnet 3.7 | 2.0 Flash |
| Context length | ~128k | ~200–500k | ~1M |
| Advantage | memory, chat-indexing, best-in-class models | writing ability, ethics-first | largest context, 50 sources, audio transcription (NotebookLM), double-check |
| Privacy | opt-in / opt-out varies by plan | always opt-in | opt-out |

- ⚠️ Privacy defaults differ by vendor AND by plan — know which version your organization has procured, and use that one for work data
- For total and complete privacy, local models are a **very promising future**

## What are "reasoning" models?

- A model is said to be "reasoning" if its final answers come after multiple inference steps (the model is given the opportunity to "introspect" on its initial outputs)
- **Consumes on the order of 10x more tokens** — the outputs you don't see cost just as much to generate as the ones you see
- ***SLOWER — you lose feedback-loop speed***

*(demo slide — live comparison of a reasoning model vs. a standard model on the same prompt)*

## When are LLMs OK to use?

Ted Chiang — award-winning sci-fi author, two collections of short stories, and the movie *Arrival* — argues in his essay "Why A.I. Isn't Going to Make Art":

> Consider **ART** as the result of **MANY SMALL, INTENTIONAL CHOICES**.
>
> A 10,000-word short story reflects at least 10,000 such decisions.
>
> When you give a model a 100-word prompt to generate a 10,000-word output, you're offloading 99% of the artistic decision-making.
>
> The result is **NOT AN EXTENSION** of your expression — it's a **DILUTION** of it.

## When are LLMs OK to use? (resolution)

**ALWAYS** — as long as they **DISPLACE** rather than **REPLACE** your OWN DECISION-MAKING

⇨ learn how to include them in **COMPLEX, DIDACTIC WORKFLOWS**

## A Hierarchy of Work

Let's **ascend** a hierarchy of work:

1. 🧱 **Survival Tasks** (repetitive, draining work)
2. 📦 **Functional Tasks** (execution-level work)
3. 🧠 **Cognitive Work** (problem solving and learning)
4. 🎨 **Creative Work** (original synthesis and expression)
5. 🧭 **Reflective Work** (purpose, values, strategy)
6. 🌐 **Meta-Work** (orchestration and systems thinking)

## LLMs Augment Us

> "The bottom line: AI won't replace you — but someone using AI will."

## LLM Energy Consumption

The energy objection, examined:

- Inference is a small portion of the energy consumption of the LLM lifecycle — roughly **40%** goes to inference, i.e., when the end-user makes calls
- Inference is currently being optimized in **MANY** ways:
  - **MoE** (mixture-of-experts architectures)
  - **Transformer ASICs** (dedicated hardware)
- And for comparison: **humans are inefficient too** — see the ACM piece "The Energy Footprint of Humans and Large Language Models"

## Let's Get Started: Listing All Tools

*(transition slide — the numbered tool spine begins here)*

## Prompting Best Practice: Separate Instructions & Data

- Some tools (like Claude or Google's NotebookLM) automatically **import pasted text as distinct files**
- **Otherwise:** use delimiters (like `"""` or `<data>`) to clearly separate:
  1. Your instructions TO the LLM
  2. The data/text you want it to process
- You can **nest** this (just use open/close quotes that are not contained in your data)

```
Summarize the key decisions in the following meeting transcript:

"""
[Paste Meeting Transcript Here]
"""

Focus on action items assigned to the 'Engineering Team'.
```

```
Here is the transcript of my lecture:
"""
[Paste Lecture Transcript Here]
"""

Here are my slides:
"""
[Paste Slides Here]
"""

How did I do in terms of pacing?
```

## Rich/Plain Text: Text is Not Created Equal

- Sources are often "rich" (formatting, layouts)
- LLMs usually prefer plain or structured text (like Markdown)
- Copy-pasting manually is tedious and error-prone
- Formatting loss can obscure meaning (e.g., lists, emphasis)

## Tool 1: Remove Rich Formatting

- The simplest move: paste **without** formatting ("Paste and Match Style" / Ctrl+Shift+V) to strip rich text down to plain text
- Use it whenever the formatting is noise rather than signal

## Tool 2: Rich Copy-Paste with Puppypaste & Markdown

- Problem: copying rich text → losing formatting
- Solution: tools that convert clipboard content to Markdown
- **Puppypaste** (website): copies rich text, pastes as Markdown
- Why Markdown? Simple, structured, LLM-friendly. Preserves lists, bold/italics, links, code blocks

## Markdown: Specify Format with Plain Text

- Markdown expresses structure in plain characters: `#` headings, `**bold**`, `*italics*`, `-` lists, `` ` `` code
- The same file is readable by humans AND perfectly structured for LLMs

## Tool 3: Clipboard Managers — Your Text Buffer

- **Problem:** copying multiple snippets sequentially is painful (copy A, paste A, copy B, paste B...)
- **Solution:** clipboard managers keep a history of copied items
- **Benefits:**
  - Access previous clipboard items
  - Cycle through recent copies
  - Search clipboard history
  - Combine multiple snippets easily
- Examples: **Keyboard Maestro** (macOS), **Pasteboard**, **ClipClip** (Windows)

## Tool 4: Clipboard "Shelves"

- Important, particularly for images and screenshots
- Also allows you to manipulate temporary files (rather than cluttering the desktop)

## Interlude: Learning Together Is Important

**AI's full potential is collective**

- Activity to map the uses everybody makes of LLMs
- Goal is to broaden each person's horizon + **prime the collective to use these tools together**
- Activity previously run with 80 students in an undergraduate course
- Should be a widespread group activity

## How AI Literacy Actually Develops

Field observations from AI-literacy research in schools describe an *acculturation* pattern, not a checklist of competencies:

1. **Personal experimentation, often kept private** — curiosity mixed with hesitation
2. **Tentative sharing with trusted colleagues or peers** — small moments of vulnerability and exchange build shared understanding
3. **Collaborative exploration and systematic integration** — once enough individual comfort exists, communities collectively reimagine their practices

The key isn't just training — it's **trust and shared experience**. This mirrors historical technology adoption (calculators, computers), with one twist: the tool itself participates in the acculturation process.

## Tool 5: Tools That Import & Export Text

### Example: Slides.com

- Presentation platform founded on **open, interoperable standards**
  - PDF is not manipulable/editable
  - PDF is very lossy — loss of structure
  - ⚠️ When PDFs are converted to text, a lot of information is destroyed
- Slides.com **uses** text in two novel ways:
  - **IMPORT:** it can create an entire presentation from a Markdown outline of your slides
  - **EXPORT:** it can export in **reveal.js** format, which is fully text

## Use Case: Slide Generation & Feedback

- **Use Case 1: Generate Markdown Slides From Your Material**
  1. Assemble syllabus, primary sources
  2. Generate Markdown from a ChatGPT/Claude/Gemini **reasoning model**: "*Generate a Markdown outline suitable for slides.com format from...*"
  3. Paste the result into slides.com or a similar Markdown-friendly slide tool
- **Use Case 2: Content + Transcript → Feedback**
  1. **Input:** slide content (text export or Markdown)
  2. **Input:** lecture transcript where slides were discussed
  3. **Prompt:** "Analyze my lecture transcript and slide content. Where were students potentially confused? Which slides need more explanation based on the discussion?"

## Where Is This Useful To You?

- Many of us manipulate tools that have both a
  - **WYSIWYG (What You See Is What You Get)** interface
  - code interface
- Usually the WYSIWYG component is very **lossy** — the computer approximates what a user might want, but poorly
- LLMs are **much more comfortable with the original representations**
- **Example:** if you are using a tool like **Intuit Mailchimp**, work with the HTML code directly

## Tool 6: Speech-to-Text — Capture Fleeting Thoughts

- Mobile LLM apps (ChatGPT, Gemini, Claude) have excellent voice input
- Native OS dictation (macOS, Windows)
- **Ask a reasoning model to structure your thoughts**
- Use it for:
  - Brainstorming on the go
  - Drafting emails/messages
  - Capturing ideas during walks or commutes

## Tool 7: Transcription As A Commodity

A short history of automatic speech recognition:

- 🔹 **First automated transcription concept:** *Audrey* (1952, Bell Labs)
- 🔹 **First consumer product:** *Dragon NaturallySpeaking* (1997)
- 🔹 **First large-scale public ASR:** *Google Voice & YouTube Captions* (~2009)
- 🔹 **First high-quality, open ASR usable by anyone:** *OpenAI Whisper* (2022)

## Where Are Transcripts?

- **Voice Memos** (Apple) — auto-transcribes your recordings
- **Lecture capture platforms** (e.g., Panopto) — transcripts of every recorded class
- **Courses on YouTube** — auto-captions on nearly everything
- **MacWhisper** — free local transcription with speaker diarization

## Use Case: Meeting/Lecture Synthesis & Analysis

- **Input:** raw transcript (from Zoom, Otter, voice memo)
- **Input:** your handwritten/typed notes (scan/type, or use speech-to-text)
- **Prompt:**

```
Analyze the following meeting transcript and my personal notes.
Generate a concise summary, list all decisions made, and extract
action items with owners and deadlines. Pay special attention to
points mentioned in my personal notes.

Transcript:
"""
[Paste Transcript]
"""

My Notes:
"""
[Paste Notes]
"""
```

## Superwhisper

*(demo slide — live demonstration of Superwhisper system-wide dictation)*

## Tool 8: Google's NotebookLM

- Has audio transcription built in
- Helps "grok" complex topics
- Upload all documents related to a topic (like vendor contracting) to research and correlate
- Can use "sourcing" and "double checking"
- *Usually a dead-end because it is hard to transfer work out of the interface (**but excellent for self-study**)*

## Your Conversations Are a Gold Mine

- All of your conversations with LLMs are valuable
- When you start engaging fully, you can have 100s of conversations a day, and it quickly adds up
- **Complex workflows involve combining and consulting with several different models**
- There are tools to help — e.g., a small open-source browser extension that exports an entire ChatGPT conversation as text (link withheld during anonymous review)

## Advanced Flow: Agent-to-Agent Communication (Manual)

- Scenario: get complex research from one model, then summarize/fact-check with a different model (e.g., Claude, or a faster/cheaper model)
- Method:
  1. Have conversation A with Model 1 (e.g., GPT-4o)
  2. Use a tool/extension (or manual copy) to export the *entire* conversation history (user prompts + AI responses)
  3. Start a new chat with Model 2
  4. **Prompt:** "Based on the following conversation I had with another AI, please [summarize / fact-check / reformat / offer a different perspective]: `"""` [Paste entire conversation A] `"""`"
- Future: protocols like A2A aim to automate this

## Tools for the Terminal

- The terminal is actually a great metaphor for what we are doing
- Three tools, briefly:
  1. **pbpaste/pbcopy:** copy/paste from the terminal
  2. **chatblade:** make single LLM calls from the terminal
  3. **claude-code, codex:** converse with LLMs from the terminal

## Tool 9: Use the Clipboard from the Terminal Too

| OS | Read | Write | Installed by default? |
|---|---|---|---|
| macOS | `pbpaste` | `pbcopy` | Yes |
| Windows | `Get-Clipboard` | `Set-Clipboard` | Yes (PowerShell) |
| WSL | `powershell.exe Get-Clipboard` | `powershell.exe Set-Clipboard` | Yes (PowerShell) |
| Linux/X11 | `xclip -selection clipboard -o` or `xsel --clipboard --output` | `xclip -selection clipboard` or `xsel --clipboard --input` | No |
| Linux/Wayland | `wl-paste` | `wl-copy` | No |

A small shell script (link withheld during anonymous review) concatenates a whole folder of files into one delimited block ready to paste into an LLM:

```
Ignore any previous versions of the files: file2.txt, file1.txt, info.json

Below is the current state of the codebase file-by-file.
===========================================================================

File 'file2.txt':
```
This is the contents of file2.txt

This will be concatenated to give the model a full overview
```

File 'file1.txt':
```
This is the contents of file1.txt

It can contain anything really
```

File 'info.json':
```
{
    "description": "This is a simple JSON file.",
    "version": "1.0"
}
```

===========================================================================
```

- Nowadays, many **terminal-based** and **UI-based** tools send whole codebases automatically
- But you can also do this manually

## Tool 10: Chatblade — Send One-Off Queries

- Open-source CLI: `github.com/npiv/chatblade`
- Pipe text in, get an LLM answer out — composable with everything else in your shell
- *Requires setting up an API key with your provider*

## Tool 11: The Agentic Clients

- Terminal-native chat agents: **Claude Code** (Anthropic), **Codex** (OpenAI)
- They read files, run commands, and converse — the clipboard flows of Tools 1–10, automated
- *(demo slide — live demonstration of an agentic client)*

## One More Thing...

Been Kim (AI interpretability researcher):

> "We are facing a communication problem. AI is doing things that seem strange, even magical. But they're only 'weird' because we haven't expanded our concepts enough to make sense of them."

See: John Hewitt, Robert Geirhos, Been Kim (Feb 2025), arXiv:2502.07586

## Reframing Understanding: Beyond Current Vocabulary

- Core idea: our current language might be insufficient to truly understand *how* complex models like LLMs work internally
- Interpretability isn't just about seeing weights; it might require new concepts and tools
- Connects back to our theme: we're developing practical *workflows* (text manipulation) even as deep *understanding* evolves

## Conclusion: You Are a Text Maestro!

- **See Everything as Text:** unlock hidden value in transcripts, notes, emails
- **Master the Flow:** use tools (speech-to-text, Puppypaste, clipboard managers) to capture, clean, and combine text efficiently
- **Structure Your Prompts:** separate instructions and data for better results
- **Integrate & Experiment:** combine sources, try agent-hopping, use text tools everywhere (browser, terminal)
- The power isn't just *in* the LLM; it's in how you *feed* and *collaborate* with it using text

## Help Everyone Else Be A Text Maestro!

- **Release all your materials in plain text:** so your students, colleagues, etc. can start combining your materials using these workflows!

---

*The session continues with the LLM Use-Cases Documentation Sprint — see ../facilitation.md. The optional "Managing Up with AI" segment (Executive TL;DR prompt scaffold + 2-minute mini-drill) is also in ../facilitation.md.*

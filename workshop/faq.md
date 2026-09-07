# Post-Workshop Questions & Answers

*Text Flows: Working Smarter with AI — from the July 2025 staff delivery.*

This FAQ merges every live-polling submission and the in-room follow-ups
from the workshop's first delivery. Answers reproduce, as faithfully as
possible, what the facilitator said live; nothing here is boilerplate.

**De-identification note:** questions are attributed to participant
labels (P1–P10), consistent across the document — the same label always
means the same person, so you can see which participants asked repeatedly.
Roles and names are withheld by design.

**Provenance note:** this document was produced with a reasoning-model
assistant from (a) the live polling submissions and (b) the workshop
transcript, under instructions to keep all details and the facilitator's
own voice — and was reviewed thoroughly after generation. It is itself an
example of the transcript-mining flow the workshop teaches.

---

## 1 · Live-Polling Questions & Answers

| # | Asked by | Question (abridged) | Answer, in polished form |
|---|---|---|---|
| 1 | **P1** | *Ethics of pasting private messages into gen-AI?* | Think in **moral-contractualist** terms: would a reasonable person object if you explained exactly what you did with their words? If yes, don't paste. Professionally, only data up to the sensitivity your institution's AI contract covers (at a US university, typically FERPA-level) may go into the sanctioned tenants; never upload HIPAA/PHI, attorney-client, or export-controlled material. When in doubt, ask — your institution likely has an internal channel for AI questions. |
| 2 | **P2** | *Why do tokens matter?* | Vendors meter and price by tokens (≈ ⅓ of a word). Token limits define the **context window** a model can hold at once (at the time: o3 Pro ≈ 128k, Claude ≈ 200k, Gemini 1.5 Pro ≈ 1M). Fewer tokens → cheaper, but also less memory. |
| 3 | **P3** | *Is Gemini the same as Copilot?* | No. **Gemini** is Google's model family; **Microsoft Copilot** is a branded UX layer that swaps underlying models (at the time, GPT-4-class). |
| 4 | **P4** | *Coping with hallucinations?* | Use **context engineering**: ① separate instructions from data with clear delimiters (`""" … """`); ② paste clean Markdown, not WYSIWYG junk; ③ fact-check with a second model; ④ switch to a **reasoning** variant for high-stakes work. |
| 5 | **P4** | *What must never be uploaded?* | Anything above your institution's contracted sensitivity level: HIPAA/PHI, export-controlled, legal privilege, etc. If you need to process such data, run a **local** model. |
| 6 | **P5** | *Why is "paste as plain text" still insufficient?* | Plain text loses document hierarchy. Convert to **Markdown** to preserve headings, lists, and emphasis; otherwise the model must guess, and links or nuanced structure vanish. |
| 7 | **P6** | *What was that clipboard-shelf tool?* | **Yoink** (macOS). Windows equivalents: *Unclutter*, *Pasteboard*. |
| 8 | **P7** | *Do LLMs read cursive?* | Multimodal models (GPT-4o, Gemini 1.5 Pro) can often parse neat cursive, but accuracy falls with stylized or faint writing. Treat it as beta. |
| 9 | **P8** | *The global AI-datacenter divide?* | Beyond the workshop's scope, but some elements: AI clusters sit mostly in the U.S., Western Europe, and coastal China. That creates latency, economic-leakage, carbon-displacement, and cultural-bias gaps. Partial mitigations: **open-weights edge models**, SaaS token pricing lowering entry costs, and publicly funded renewable regional datacenters. *Inequity is real, not destiny.* |
| 10 | **P2** | *Are MacWhisper / superwhisper free?* | Yes — fully usable free tiers; the one-time "Pro" license just unlocks longer files and faster models. |
| 11 | **P9** | *Good online learning guides?* | None rise above "tourist" level yet. Grow **internal** workshops and curated pages together — that's the collaborative pillar. |
| 12 | **P7** | *Does AI recognize politeness ("please", "thank you")?* | Always be polite — **not** because the model keeps a naughty-or-nice list, but because we have only one linguistic interface and it *changes us*. If you spend the day barking at chatbots, that habit will leak into your emails. Use "please" and "thank you" as deliberate self-training. |
| 13 | **P1** | *Creative-writing use?* | Treat the model as an **iterative co-writer**: seed it with your plot/voice notes, then refine through dozens of micro-edits. Ownership rises with each iteration; the aim is *displacement* (amplifying your decisions), never *replacement* of artistry. |
| 14 | **P4** | *Models "run away" and over-produce — how to curb?* | Be blunt: "Do **not** add an intro or outro. Limit to two paragraphs." For length-exactness, use a reasoning model and specify a hard token or word budget. |
| 15 | **P10** | *Keeping tool chaos tidy?* | A working stack: system clipboard history (Keyboard Maestro on Mac; **Win + V** or *Clipboard Master* on Windows), a Yoink shelf for temp files, [Echoes](https://echoes.r2bits.com) for searchable chat history, and clearly named folders for meeting transcripts. The goal is to keep your mind in the *iterative* zone, not file-shuffling. |

---

## 2 · Follow-up Questions Raised Verbally

### Q-1 "Is a *reasoning* model like those astrology sites — does it just ask for more inputs first?"

**Context:** the questioner meant sites that take your birth time/place and then generate a multistep report.
**Answer:** No — if you'd like the model to "ask you anything it might need to come up with an answer," you can request that explicitly in any model: "*Please ask me anything you need to know to come up with a better answer.*"

The difference with a reasoning model is that it can look at its own answer before sharing it with you — and might change it. This matters for math and multi-step judgment calls. (Models typically already do this when generating a deep-research report.)

### Q-2 "So tokens are basically how much text the AI can *comprehend* at once, right?"

Exactly. The *context window* is the model's working memory; once you exceed it, older tokens fall off the back.

### Q-3 "What's the Chrome extension you used to copy a whole chat transcript?"

A small open-source Chrome extension that copies an entire conversation thread to your clipboard in one click, for pasting into another model or into [Echoes](https://echoes.r2bits.com). *(Link withheld during the double-blind review period — it identifies the author; it will be restored here afterward. Several similar "conversation copier / exporter" extensions exist in the Chrome Web Store.)*

### Q-4 "Could you outline the 30% you disagree on with Ted Chiang?"

Chiang's claim: *people will always use LLMs exploitatively — one-sentence prompt, 10k-word story — so the output dilutes authorship and art.*
The push-back: iterative users feed 100-word briefs, then make **scores** of micro-edits, each restoring intent. Authorship lives in the iteration loop, not the first prompt. *Depth of engagement*, not tool presence, determines originality.

### Q-5 "A Windows alternative to Keyboard Maestro's clipboard history?"

Two free options:

* **Built-in:** press **Win + V** to open Windows' native clipboard history (enable once in Settings).
* **Clipboard Master:** full-featured freeware — [clipboardmaster.com](https://www.clipboardmaster.com).

### Q-6 "How do I make a model stick to exactly 200 words when it 'can't count'?"

Non-reasoning models genuinely *cannot* count; they rely on fuzzy length heuristics. Use a **reasoning** variant and add a *post-check loop*:

1. "Draft a 200-word blurb …"
2. "Count your words and revise until count = 200."

Even then expect ±3 words; perfect compliance may require external post-processing.

### Q-7 "Does pasting rich text matter if it's only an outline of headings?"

Less critical, but still lossy: the model may blur *Section 2* vs. *Sub-section 2.1*, and you'll lose embedded links. For outlines, paste the Markdown export — hierarchy preserved, no formatting cruft.

### Q-8 "If I record every meeting, how do I keep transcripts searchable?"

Two paths:

* **Filesystem discipline** — save `.txt` files in a dated folder structure.
* **Chat-per-meeting workflow** — start a new LLM thread per meeting, paste the transcript, then tag that chat via **[Echoes](https://echoes.r2bits.com)**. Echoes' search instantly dredges up any snippet across all meetings; NotebookLM can further cluster by project.

---

## 3 · Dated corrections for current reuse (September 2026)

The answers above reproduce what was said live in July 2025, and two of
them contain errors we preserve rather than silently rewrite (the FAQ is
a historical record); correct them when reusing:

- **Q2 (tokens)**: a token is roughly **three-quarters** of an English
  word (so ~750 words ≈ 1,000 tokens), not one-third; the ratio varies
  by language and tokenizer.
- **Q7 (shelf tools)**: **Unclutter is macOS software**, not a Windows
  equivalent. For Windows shelves, see DropPoint or Dropshelf (as in
  the worksheet); Pasteboard also offers a Windows product.

## 4 · Quick-Reference Links

* **Yoink** (macOS shelf) — [eternalstorms.at/yoink](https://eternalstorms.at/yoink/)
* **MacWhisper / superwhisper** — [goodsnooze.gumroad.com](https://goodsnooze.gumroad.com/l/macwhisper) / [superwhisper.com](https://superwhisper.com/)
* **Echoes chat search** — [echoes.r2bits.com](https://echoes.r2bits.com)
* **NotebookLM** — [notebooklm.google.com](https://notebooklm.google.com/)
* **Clipboard Master** (Windows) — [clipboardmaster.com](https://www.clipboardmaster.com)
* **Win + V** setup — [microsoft.com/windows/tips/clipboard-history](https://www.microsoft.com/windows/tips/clipboard-history)

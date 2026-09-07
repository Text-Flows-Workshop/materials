# Tool Installation Guide — Windows · macOS · Linux

*Companion to the Text Flows participant worksheet. None of these tools are
required — each one just removes a little friction from working with text.
Install the ones that speak to you, skip the rest, and if your machine is
locked down, jump straight to [No-install fallbacks](#no-install-fallbacks)
at the end: the skills work even with zero installs.*

**How to read each entry:** where to get it → what it costs → one first-run
tip → one quick way to check it's working.

---

## 1. Formatting Cleaners

When you copy text, you usually get **rich text** — fonts, colors, weird
spacing — along for the ride. These tools let you paste **plain text** on
purpose, so your prompts and documents stay clean.

### PastePlainText (macOS, free)

- **Get it:** Mac App Store — search "Paste Plain Text", or visit
  <https://apps.apple.com/us/app/paste-plain-text/id1528231008?mt=12>
- **Cost:** Free.
- **First-run tip:** It lives in your menu bar (top-right of the screen),
  not in the Dock — look for its small icon after launching.
- **Verify:** Copy a headline from any web page, use the app's shortcut to
  paste into Notes. If the text arrives without the web page's font and
  color, it's working.

### Puppypaste (any OS, web, free)

- **Get it:** Nothing to install — go to <https://puppypaste.com>.
- **Cost:** Free.
- **First-run tip:** Paste rich text into the box; copy the cleaned result
  back out. Bookmark it.
- **Verify:** Paste a chunk of a formatted email in; what you copy back out
  should be plain, tidy text (with the structure, like headings and links,
  preserved as Markdown).

### Built-in paste-plain shortcuts (all OSes, free)

- **Windows / Linux:** `Ctrl + Shift + V` pastes without formatting in most
  browsers and many apps.
- **macOS:** `Cmd + Option + Shift + V` ("Paste and Match Style") does the
  same in most apps.
- **Verify:** Copy formatted text, try the shortcut in a document — the
  fancy formatting should be gone.

---

## 2. Clipboard Managers

A clipboard manager remembers the last *many* things you copied, instead of
just the last one — a big deal when you're moving several snippets between a
document and an AI chat.

### Windows built-in clipboard history (free)

- **Get it:** Already on your machine. Enable once: **Settings → System →
  Clipboard → Clipboard history → On** (or just press `Win + V` and click
  **Turn on**).
- **Cost:** Free.
- **First-run tip:** You can pin snippets you reuse often (the pin icon) so
  they survive restarts.
- **Verify:** Copy two different things, press `Win + V` — you should see
  both.

### ClipClip (Windows, free)

- **Get it:** <https://clipclip.com>
- **Cost:** Free.
- **First-run tip:** It runs quietly in the system tray (bottom-right,
  near the clock). Open its settings once to see its paste hotkey.
- **Verify:** Copy a few snippets, press ClipClip's hotkey — a list of your
  recent copies should pop up.

### Keyboard Maestro (macOS, paid)

- **Get it:** <https://www.keyboardmaestro.com/main/>
- **Cost:** Paid, one-time purchase; free trial available. (It does far
  more than clipboards — it's a full automation tool — but its clipboard
  history alone can be worth it.)
- **First-run tip:** macOS will ask you to grant it Accessibility
  permissions in **System Settings → Privacy & Security** — it needs these
  to paste for you; this is expected.
- **Verify:** Copy two different things, then open the *Clipboard History
  Switcher* (its hotkey is shown in the app) — both should be there.

### CopyQ (Linux — also works on Windows and macOS, free)

- **Get it:** Your distribution's software center (search "CopyQ"), or
  `sudo apt install copyq` on Ubuntu/Debian. Downloads for all OSes at
  <https://hluk.github.io/CopyQ/>.
- **Cost:** Free and open source.
- **First-run tip:** Assign a global shortcut for "Show/hide main window"
  in **Preferences → Shortcuts** — that's how you'll actually use it.
- **Verify:** Copy a few snippets, press your shortcut — your clipboard
  history appears in a searchable list.

---

## 3. Shelves

A "shelf" is a small landing zone on your screen where you can drag text
snippets, files, and screenshots, then drag them out later — handy when
you're gathering context (like screenshots) to share with a model.

### Yoink (macOS, paid)

- **Get it:** Mac App Store, or <https://eternalstorms.at/yoink/>
- **Cost:** Small one-time purchase (a free trial is available from the
  website).
- **First-run tip:** Start dragging any file or selected text toward the
  edge of the screen — the shelf appears automatically to catch it.
- **Verify:** Drag a screenshot onto the shelf, then drag it from the shelf
  into a chat window.

### DropPoint (Windows, free)

- **Get it:** <https://droppoint.netlify.app/>
- **Cost:** Free.
- **First-run tip:** Start a drag and the drop bubble appears; you can
  stack multiple items before dropping them anywhere.
- **Verify:** Drag a file onto the bubble, then drag it out into another
  folder or a chat window.

### Dropshelf (Windows, paid)

- **Get it:** Microsoft Store —
  <https://apps.microsoft.com/detail/9mzpc6p14l7n>
- **Cost:** Small one-time purchase.
- **First-run tip:** Drag toward the screen edge to summon a shelf, much
  like Yoink on macOS.
- **Verify:** Same test: drag a file in, drag it back out somewhere else.

### Linux equivalent: Collector (GNOME, free)

- **Get it:** Flathub — search "Collector" in your software center.
- **Cost:** Free and open source.
- **First-run tip:** Drag items into its window to stack them; drag them
  out when you need them. (No shelf app on your desktop? A folder kept
  open in a corner of the screen is a perfectly good low-tech shelf.)
- **Verify:** Drag a file in, drag it back out.

---

## 4. Speech-to-Text

Talking to a model is often better than typing: you skip the work of
pre-structuring your thoughts, and useful details slip out. Modern local
transcription can turn an hour of audio into text — with speaker labels —
in about 30 seconds.

### MacWhisper (macOS, free version + paid Pro)

- **Get it:** <https://goodsnooze.gumroad.com/l/macwhisper>
- **Cost:** Free version is genuinely useful; a one-time Pro upgrade adds
  larger (more accurate) models and features like speaker identification.
- **First-run tip:** It will download a transcription model the first time
  — start with a small model; you can add bigger ones later. Everything
  runs on your machine; audio doesn't leave it.
- **Verify:** Record ten seconds of yourself talking, drop the recording
  in, and read the transcript.

### superwhisper (macOS; Windows in beta; free tier + subscription)

- **Get it:** <https://superwhisper.com/>
- **Cost:** Free tier to start; subscription for the full experience.
- **First-run tip:** Grant the microphone and accessibility permissions it
  asks for — it types the transcription directly wherever your cursor is,
  which is the whole magic.
- **Verify:** Put your cursor in any text field, hold the hotkey, say a
  sentence, release — the words should appear where you were typing.

### WhisperTyping (Windows, free to try)

- **Get it:** <https://whispertyping.com>
- **Cost:** Free to try; check the site for current pricing.
- **First-run tip:** Like superwhisper, it types where your cursor is —
  learn the push-to-talk hotkey first.
- **Verify:** Cursor in a document, hotkey, speak, watch the words land.

### Linux equivalent: Speech Note (free)

- **Get it:** Flathub — search "Speech Note" in your software center.
- **Cost:** Free and open source.
- **First-run tip:** In its settings, download a Whisper model for your
  language; transcription then runs entirely offline.
- **Verify:** Record a short note in the app and read the transcript.

### ChatGPT / Claude voice input (any OS, no install)

- The chat apps and websites have a microphone button built in — see
  [No-install fallbacks](#no-install-fallbacks).

---

## 5. Conversation Management

Your past conversations with models are a real archive: prompts you
polished, explanations you want back. These tools make that archive
searchable.

### Echoes (Chrome extension — Windows, macOS, Linux; free)

- **Get it:** <https://echoes.r2bits.com> — it will take you to the Chrome
  Web Store listing.
- **Cost:** Free.
- **First-run tip:** Pin the extension (puzzle-piece icon → pin) so it's
  one click away. Browser extensions usually install without administrator
  rights, so this often works even on managed machines.
- **Verify:** Have a short conversation in ChatGPT or Claude, then search
  for a word from it in Echoes — the conversation should come up.

---

## 6. Terminal Utilities

The terminal (Terminal on macOS, PowerShell on Windows) looks intimidating
but earns its keep with one trick: moving text between files and your
clipboard in a single command. Nothing to install on Windows or macOS.

### macOS: `pbcopy` and `pbpaste` (built in, free)

- **Get it:** Already there. Open **Terminal** (find it with Spotlight:
  `Cmd + Space`, type "Terminal").
- **Verify:** Type `pbpaste` and press Return — whatever you last copied
  prints out. Then try `pbcopy < somefile.txt` to copy a whole file.

### Windows: `Get-Clipboard` and `Set-Clipboard` (built in, free)

- **Get it:** Already there. Open **PowerShell** from the Start menu.
- **Verify:** Copy some text anywhere, then type `Get-Clipboard` and press
  Enter — your text prints out. `Set-Clipboard "hello"` works the other
  way.

### Linux: `xclip` or `wl-clipboard` (free)

- **Get it:** `sudo apt install xclip` (X11 sessions) or
  `sudo apt install wl-clipboard` (Wayland sessions — the default on
  modern Ubuntu and Fedora). Not sure which you have? Install both; they're
  tiny.
- **Verify:** Copy some text anywhere, then run `wl-paste` (Wayland) or
  `xclip -o -sel clip` (X11) — your text prints out.

---

## 7. CLI & Agentic Clients

The most technical section — completely optional, and best saved for after
the rest feels comfortable. These tools let you chat with models from the
terminal, or hand them multi-step tasks.

### Chatblade (all OSes, free + API costs)

- **Get it:** <https://github.com/npiv/chatblade> — installed with Python's
  `pip install chatblade` (ask a technical colleague for a hand if that
  sentence is new to you).
- **Cost:** The tool is free; it needs an API key, which is billed by
  usage (typically pennies for casual use).
- **First-run tip:** Set your API key once as described in its README.
- **Verify:** `chatblade "say hello"` should get you a reply in the
  terminal.

### Claude Code (`claude`) (all OSes, free tool + subscription/API)

- **Get it:** Follow the official install instructions at
  <https://code.claude.com/docs> (there is a simple one-line installer).
- **Cost:** The tool is free; it signs in with a Claude subscription or an
  API key.
- **First-run tip:** Run it *inside a folder of files you want help with*
  — that's its natural habitat.
- **Verify:** Type `claude` in a terminal; you should get an interactive
  prompt after signing in.

### Codex CLI (`codex`) (all OSes, free tool + subscription/API)

- **Get it:** Official instructions at
  <https://github.com/openai/codex>.
- **Cost:** Free tool; signs in with a ChatGPT account or API key.
- **Verify:** Type `codex` in a terminal and sign in.

### AI-native editors: Cursor and Windsurf (Windows, macOS, Linux)

- **Get them:** <https://cursor.com> and <https://windsurf.com> — these are
  ordinary desktop apps with ordinary installers, the gentlest entry point
  in this whole section.
- **Cost:** Both have free tiers; paid plans for heavier use.
- **Verify:** Open a folder of documents in the editor and ask the built-in
  chat a question about them.

---

## No-install fallbacks

*For locked-down machines — a very common situation on managed work
computers. You can do the entire workshop with just these.*

| Need | Fallback (nothing to install) |
| --- | --- |
| Paste as plain text | `Ctrl + Shift + V` (Windows/Linux), `Cmd + Option + Shift + V` (macOS) |
| Formatting cleaner | <https://puppypaste.com> in any browser |
| Clipboard history | `Win + V` on Windows (built in — enable once) |
| Speech-to-text | `Win + H` (Windows dictation); the dictation/mic key on macOS (enable in **System Settings → Keyboard → Dictation**) |
| Voice input to a model | The microphone button in the ChatGPT or Claude app/website |
| Conversation search | Browser extensions (like Echoes) usually install without admin rights |
| Shelf | A folder kept open in the corner of your screen |

If even Settings are locked (you can't turn on `Win + V`, say), that's a
quick request to your IT support desk — these are standard, low-risk
features, and it's a reasonable thing to ask for.

---

*Part of the Text Flows workshop materials. Tools and prices drift; the
habit of keeping text clean, findable, and speakable is the durable skill.*

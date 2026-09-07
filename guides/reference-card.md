# Keyboard & Clipboard Reference Card

*Text Flows workshop — print this page and keep it by your keyboard.*

## Copy · Paste · Paste-Plain

| Action              | Windows        | macOS               | Linux          |
| ------------------- | -------------- | ------------------- | -------------- |
| Copy                | Ctrl+C         | Cmd+C               | Ctrl+C         |
| Cut                 | Ctrl+X         | Cmd+X               | Ctrl+X         |
| Paste               | Ctrl+V         | Cmd+V               | Ctrl+V         |
| Paste plain (no     | Ctrl+Shift+V   | Cmd+Opt+Shift+V     | Ctrl+Shift+V   |
| formatting)         |                | ("Match Style")     |                |
| Select all          | Ctrl+A         | Cmd+A               | Ctrl+A         |

Web cleaner for stubborn formatting: **https://puppypaste.com**

## Clipboard History

| OS      | How to open it                                              |
| ------- | ----------------------------------------------------------- |
| Windows | **Win+V** (enable once: Settings > System > Clipboard)      |
| macOS   | Your clipboard manager's hotkey (e.g. Keyboard Maestro's    |
|         | Clipboard History Switcher — hotkey shown in the app)       |
| Linux   | **CopyQ** — assign a global "show window" shortcut in its   |
|         | Preferences, then press it                                  |

## Start Dictation

| OS      | Shortcut / method                                           |
| ------- | ----------------------------------------------------------- |
| Windows | **Win+H** (built-in dictation)                              |
| macOS   | Press the mic/dictation key, or the shortcut set in         |
|         | System Settings > Keyboard > Dictation                      |
| Linux   | Speech Note app (Flathub), or the mic button in the chat    |
| Any     | Microphone button in the ChatGPT / Claude app or website    |

## Terminal Clipboard One-Liners

| OS / shell     | Copy file to clipboard            | Paste clipboard    |
| -------------- | --------------------------------- | ------------------ |
| macOS          | `pbcopy < notes.txt`              | `pbpaste`          |
| Windows        | `Set-Clipboard`                   | `Get-Clipboard`    |
| (PowerShell)   | `  (Get-Content notes.txt)`       |                    |
| Linux (X11)    | `xclip -sel clip < notes.txt`     | `xclip -o -sel clip` |
| Linux (Wayland)| `wl-copy < notes.txt`             | `wl-paste`         |

Handy combo: transcribe or draft → clean it → `pbcopy` → paste anywhere.

## The Delimiter Pattern

Separate **instructions** (yours) from **data** (pasted) with `"""` fences:

```
Summarize the notes below in three bullet points
for a colleague who missed the meeting.

"""
<paste the raw meeting notes here>
"""
```

Rule of thumb: *your words outside the fences, pasted material inside.*
The model then never confuses something in the pasted text for an
instruction from you.

---

*Text is the interface. Keep it clean, keep it plain, keep it moving.*

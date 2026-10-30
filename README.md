<h1 align="center">⚡ Gboard Turbo-Type</h1>

<p align="center">
  <b>Your Gboard, now an AI voice keyboard.</b><br>
  Talk, and the text is there. Rewrite it with one tap.
</p>

<p align="center">
  <a href="https://morphe.software/add-source?github=bjspi/gboard-turbotyper-patches&name=Gboard%20Turbo-Type"><img alt="Add to Morphe" src="https://img.shields.io/badge/Morphe-Add%20Source-00A8FF?style=for-the-badge"></a>
  <img alt="Version" src="https://img.shields.io/badge/version-3.11.128-success?style=for-the-badge">
  <img alt="Gboard" src="https://img.shields.io/badge/Gboard-18.0.3-4285F4?style=for-the-badge">
  <img alt="License" src="https://img.shields.io/badge/license-GPL--3.0-lightgrey?style=for-the-badge">
</p>

---

Turbo-Type is a set of patches for **Gboard 18.0.3**, applied with [Morphe](https://morphe.software). It is built on the excellent Gboard patches by **Jason Wu** ([jasonwu1994/Gboard-patches](https://github.com/jasonwu1994/Gboard-patches), "Gboard WU") and keeps every one of them, then adds a complete layer for **fast dictation, LLM rewriting and smart replies**.

## ✨ Highlights

### 🎙️ Dictation that keeps up with you
- Tap the mic in Gboard's header and speak; the transcript lands **directly in the text field**, typically within a few hundred milliseconds of stopping.
- A compact recording bar with your prompts, a timer and an animated light run. Long-press to discard without uploading anything.
- **Custom vocabulary** and per-language transcription prompts for names, brands and jargon.

### ⚡ Pick your engine
| Provider | Mode |
|---|---|
| **Groq Whisper** | Direct upload, or via your own backend with smart routing, or **both routes racing in parallel** (fastest wins). Add several API keys and they **rotate automatically**. |
| **OpenAI** | GPT transcription as file, realtime or live stream |
| **Google Gemini** | Transcribe Live over WebSocket, or file based |
| **fal.ai** | Whisper / Wizper Large v3 |
| **Fireworks** | Whisper |

Connections are pre-warmed while you speak, so the request is ready the moment you stop.

### 🪄 Rewrite with LLMs
- Your own prompts as **one-tap buttons**: during recording, on selected text, or dragged into **Gboard's toolbar** as tools with a text or **full-color emoji** label.
- **Instant Prompting:** say a trigger word plus an instruction ("Instruction: make this a polite English email") and get the finished text.
- Works with Groq, OpenAI, Gemini or **any OpenAI-compatible API** you add yourself (name, icon, URL, key, model list), including reasoning-effort control for supported models.
- Prompts can also be **edited from a computer over ADB**, see below.

### 💬 Reply on screen
Answer a chat from a **screenshot** or the **clipboard**, optionally guided by a short spoken hint.

### 🧰 Everyday tools
- Select all, copy and cut as toolbar tools; **3 to 8 items** on Gboard's top toolbar.
- Saved recordings can be retried or discarded; haptic feedback, diagnostics and log export.

## 🚀 Install

1. Install [Morphe](https://morphe.software) on Android.
2. Add this source: **[tap here](https://morphe.software/add-source?github=bjspi/gboard-turbotyper-patches&name=Gboard%20Turbo-Type)**, or paste `github.com/bjspi/gboard-turbotyper-patches` as a patch source.
3. Patch **Gboard 18.0.3** and pick the patches you want.
4. Open Gboard settings → **Turbo-Type** and enter your API key(s).

Morphe checks `patches-bundle.json` on `main` and offers an update whenever a new version is published. `patches-gboard.mpp` always holds the newest build.

## 🔧 Edit prompts over ADB

Read and change the rewording prompts from a computer instead of typing on the phone. Only the ADB shell has access. The built-in help lists every command with your installation's address filled in:

```bash
adb shell content read --uri content://com.google.android.inputmethod.latin.turbotype_connections/help
```

If you renamed the package while patching, find the address first:

```bash
adb shell "dumpsys package providers | grep -o '[A-Za-z0-9._]*turbotype_connections' | sort -u"
```

The most common commands (`B` = `content://com.google.android.inputmethod.latin.turbotype_connections`):

| Task | Command |
|---|---|
| Back up / view all prompts (JSON list in button order) | `adb shell content read --uri B/prompts > prompts.json` |
| Replace one prompt's instruction (name and icon stay) | `adb shell content write --uri B/prompts/<id or name> < instruction.txt` |
| Change single fields, e.g. `{"name": "New"}` | `adb shell content write --uri B/prompts/<id or name> < change.json` |
| Replace all prompts | `adb shell content write --uri B/prompts < prompts.json` |
| Delete one prompt | `adb shell content delete --uri B/prompts/<id or name>` |
| Check the last write (`ok …` or `error …`) | `adb shell content read --uri B/prompts_status` |

Every write is checked completely first; a broken file changes nothing. `adb` exits with 0 even on errors, so check `prompts_status`.

## 🔐 Privacy

Bring your own API keys. Audio and text go only to the providers you configure; nothing is sent anywhere otherwise. Keys are stored on your device.

## 📄 License & credits

GPL-3.0, like the upstream project. Huge thanks to [Jason Wu](https://github.com/jasonwu1994/Gboard-patches) for the foundation.
Morphe is referenced for compatibility only. This project is not affiliated with Morphe or Google.

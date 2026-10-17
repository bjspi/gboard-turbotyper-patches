# Changelog

# 3.11.120 (2026-10-17)

Nur diese first, with a "1" icon

### Changes

* **Gboard:** In the Transkribieren choice, "Nur diese" now comes first, before "Mit Sammlung", and has a simple "1" icon.

# 3.11.119 (2026-10-17)

Replies keep the voice note collection

### Changes

* **Gboard:** A reply with R no longer removes the voice notes it used, so a reply that did not fit can simply be made again. The collection now only ends with Neue Sammlung or 15 minutes after the newest voice note.

# 3.11.118 (2026-10-17)

Transcribe only this voice note or with the collection

### Changes

* **Gboard:** When voice notes are collected, Transkribieren in the share menu asks: "Mit Sammlung" (e.g. 3 gesammelte + diese = 4 Sprachnachrichten) or "Nur diese", which reads only the shared note and leaves the collection unchanged.
* **Gboard:** Clearer text for Neue Sammlung: "Verwirft die 3 bisherigen und beginnt mit dieser neu".

# 3.11.117 (2026-10-17)

Transcript separators, list icon for Sammeln

### Changes

* **Gboard:** In the transcript overlay a "----------" line separates the transcripts of several voice notes.
* **Gboard:** "Sammeln" in the share menu has a list icon.

# 3.11.116 (2026-10-17)

One voice note collection, Neue Sammlung

### Changes

* **Gboard:** Voice notes go into one collection for both Transkribieren and R. Transkribieren shows the shared note together with everything collected and no longer clears the collection; R still removes the notes it used. The collection expires 15 minutes after the newest note.
* **Gboard:** The share menu is now Transkribieren (shows e.g. "3 gesammelt + diese = 4"), Sammeln and, when something is collected, Neue Sammlung, which drops the earlier notes and starts over with the shared one.
* **Gboard:** The Zusammenfassen button in the transcript overlay has its own row, so Kopieren no longer wraps.

# 3.11.115 (2026-10-17)

Share entry labeled with the app name

### Changes

* **Gboard:** The single share entry for voice notes is labeled with the app's own name (Gboard) again instead of "Turbo-Type".

# 3.11.114 (2026-10-17)

One share entry with a fixed-order menu

### Changes

* **Gboard:** Sharing a voice note now shows a single "Turbo-Type" entry. It opens a menu with Transkribieren, Für Transkription sammeln and Für Antwort sammeln, always in this order, each with an icon and the number of notes already collected.
* **Gboard:** New setting "Ein Eintrag im Teilen-Menü" (on by default). Off brings back the three separate share entries, which Android sorts by usage.

# 3.11.113 (2026-10-15)

One reply prompt, Antwort auf Kontext as its own menu

### Changes

* **Gboard:** Replies via R use a single system prompt for every context (voice notes, clipboard, screenshot); the context tags tell the model what it gets. Unedited earlier per-context prompts are dropped automatically.
* **Gboard:** "Antwort auf Kontext" is its own entry in the Turbo-Type main menu, right below Umformulieren: source, voice note collection, own context, reply prompt and model.

# 3.11.112 (2026-10-15)

Collect voice notes for one transcript, summary button

### Changes

* **Gboard:** Share sheet order: Transkribieren, Für Transkription sammeln, Für Antwort sammeln.
* **Gboard:** New share entry "Für Transkription sammeln": collects voice notes without a dialog and transcribes them in the background. The next "Transkribieren" shows all of them together, oldest first; closing the overlay ends that collection. It is separate from the collection for replies.
* **Gboard:** The transcript overlay has a "Zusammenfassen" button: the transcript is rewritten with your summary prompt by the rewording provider; "Original" switches back, Kopieren copies what is shown.
* **Gboard:** New setting "Prompt für Zusammenfassen" under Umformulieren > Sprachnachrichten transkribieren, with a default that lists the key points and everything that needs your reaction.

# 3.11.111 (2026-10-15)

Voice notes as reply context, transcribe shared voice notes

### Changes

* **Gboard:** Two new share sheet entries for voice notes (WhatsApp and other apps): "Für Antwort sammeln" collects without a dialog and transcribes each note right away in the background; "Transkribieren" shows a voice note as text in an overlay with Kopieren.
* **Gboard:** Toolbar R uses collected voice notes as context: the bar shows a voice chip next to clipboard and screenshot, preselected when notes are collected. After the reply is written exactly those notes are removed; a collection expires 15 minutes after the last shared note.
* **Gboard:** Own system prompt for replies to voice notes, editable under Antwort auf Kontext.
* **Gboard:** New setting "Eigener Kontext für Antworten": standing context (who you are, tone, address) sent with every reply via R.
* **Gboard:** Shorter source chips while recording a reply (🎙 n, 📋, 📷).
* **Gboard:** Shared mp3, webm and flac audio is accepted for transcription.

# 3.11.110 (2026-10-15)

Paste tool, reply recording starts at once, clipboard chip switch

### Changes

* **Gboard:** New toolbar tool "Einfügen" (clipboard with a down arrow): pastes the current clipboard at the cursor, also in password fields. Drag it into the toolbar like Copy and Cut.
* **Gboard:** New switch in Turbo-Type > Darstellung for the clipboard chip in the suggestion bar (recently copied text or image). It is Gboard's own setting from Gboard > Clipboard, so both always match and it applies at once.
* **Gboard:** Toolbar R is now called "Antwort auf Kontext".
* **Gboard:** R starts recording at once when text was copied. While recording, the bar shows Zwischenablage (preselected) and Screenshot next to the timer; Screenshot asks for the screen capture and then records again, switching back to the clipboard keeps the recording. The "Antwort-Hinweis" label is gone.
* **Gboard:** Whisper temperature is set with a slider (0 to 1 in steps of 0.05) plus "Nicht senden"; values chosen before stay valid.

# 3.11.109 (2026-10-15)

Transcription prompts and Whisper temperature

### Changes

* **Gboard:** New default transcription prompts for German and English, the same instruction prompts as the WhisperTyper desktop app. In a Groq Whisper benchmark they kept punctuation and capitalization without the dropped or rewritten passages the short sample-sentence prompts sometimes caused. Prompts you never edited are updated; your own prompts stay as they are.
* **Gboard:** New "Whisper-Temperatur" setting below the Whisper model for Groq and Groq via backend: 0 (default, the same recording always gives the same text), 0.1 to 1, or not sent at all. Previously no temperature was sent.

# 3.11.108 (2026-10-09)

Robust colored emoji toolbar icons

### Changes

* **Gboard:** Emoji prompt tools in Gboard's toolbar are recognized in three independent ways: the bitmap itself (now kept alive), an invisible marker in the bitmap, or the key's description matching the prompt label. Any one is enough to show the emoji in its own colors.
* **Gboard:** A guard re-applies the colored icon if Gboard swaps the key icon later, for example after a theme or state change.
* **Gboard:** Diagnostics log how each toolbar key icon was matched.

# 3.11.107 (2026-10-09)

Update delivery check

### Changes

* **Gboard:** No functional changes; this release verifies that Morphe offers the update and re-patch for Gboard straight from this source.

# 3.11.106 (2026-10-09)

Emoji toolbar icons stay colored

### Changes

* **Gboard:** Emoji prompt tools in Gboard's toolbar are now recognized by an invisible marker in their bitmap instead of by object identity. Gboard shows a copy of the icon bitmap, so the previous lookup failed once the originals were garbage-collected and the emoji turned into a black silhouette again.
* **Gboard:** Project rules: one version per work round, one clean release commit at the end, automatic publishing to the public Morphe source.

# 3.11.105 (2026-10-09)

Toolbar order fix, colored emoji tools, one-time default prompts

### Changes

* **Gboard:** Toolbar count (WU access point count patch): Gboard stores how many items the user left on the bar after rearranging (mku.f); a new hook records that, so the configured count no longer pulls an overflow item back onto the bar on every keyboard start. Changing the configured count applies it again until the user rearranges once more.
* **Gboard:** Prompt tools with an emoji label keep their colors in Gboard's toolbar: the emoji bitmap (also inside Gboard's Inset/LayerDrawable wrappers) is swapped for a drawable that ignores the theme's tint and color filter. Emoji and text labels are drawn larger to match the vector icons.
* **Gboard:** Default prompts EN and W are seeded once per installation only; deleted defaults no longer come back with an update.
* **Gboard:** Recording bar: prompt chips with 20 % less horizontal padding.
* **Gboard:** "Aufnahme verworfen" is shown for 600 ms instead of 765 ms.

# 3.11.98 (2026-10-07)

Parallel routes use two keys, race settings, race logging

### Changes

* **Gboard:** "Beide Wege parallel" reserves two consecutive Groq keys up front, so the direct leg and the backend-URL leg never share a key (given 2+ keys).
* **Gboard:** The setting moves below "Chunk-Intervall (danach)". While it is on, "Direktes Groq bei langsamem Backend", "Bei schnellem Netz direkt zu Groq" and "Vorsprung für Direkt-Upload" are greyed out with a note.
* **Gboard:** Logging for adb: route_settings lists the effective routing settings per dictation; groq_key_selected names the legs; race_started/race_finished, leg_won, leg_discarded and leg_loser (state at the moment the winner was taken) show exactly which leg won and what happened to the other one.

# 3.11.95 (2026-10-07)

Rotate multiple Groq API keys for transcription

### Changes

* **Gboard:** The Groq key field accepts several keys separated by comma, semicolon or whitespace; duplicates are ignored. The settings row shows how many keys are configured.
* **Gboard:** Every Groq transcription request (direct, backend URL, retries, and the Rambler path) takes the next key round-robin. Checks, the benchmark and the shared rewording key keep using the first key.
* **Gboard:** Diagnostics log "groq_key_selected key=N/M" per request; the key itself is never logged.

# 3.11.93 (2026-10-07)

Reply source choice, Full Log, reply and transcription prompts

### Changes

* **Gboard:** Reply (toolbar R): "Quelle für Antworten" replaces the clipboard switch. Default "Jedes Mal fragen": with text on the clipboard the toolbar offers Zwischenablage / Screenshot; an empty clipboard goes straight to the screenshot. Sensitive clipboard content (passwords) is never used.
* **Gboard:** Clipboard text is sent between <zwischenablage> tags as pure context; the spoken input is labelled as the user's instruction with priority.
* **Gboard:** New default reply prompts (screenshot and clipboard) with an explicit ranking: instruction first, context second; unedited old defaults are replaced. Both prompts are always editable in the settings.
* **Gboard:** Full Log switch (Diagnose): transcripts, transcription prompt, custom words, full request (system and user), answer and inserted text go to the diagnostics log; never keys or audio. Long texts are split into parts.
* **Gboard:** Transcription prompts no longer name filler words: Whisper imitated them and wrote "ähm". Unedited old defaults are migrated on start.

# 3.11.87 (2026-10-07)

Clipboard reply, settings icons, request logging, T-menu modal

### Changes

* **Gboard:** Settings rows use drawn line icons chosen per row instead of guessed Unicode glyphs (many rows showed the same circled dot or a bare bullet).
* **Gboard:** Reply (toolbar R): optional "Zwischenablage statt Screenshot" switch. No capture consent; the newest clipboard text is the context, previewed in the header for the first seconds; an empty clipboard shows a hint. Own system prompt; the text is stored in the job so Retry works.
* **Gboard:** Reply diagnostics: screenshot brightness at capture, attached image metadata (size, SHA-256 prefix, base64 length), request body check and response token usage; the last sent screenshot can be exported.
* **Gboard:** Every HTTP request logs its URL (without query) and model; backend actions and live WebSocket connections log theirs as well.
* **Gboard:** Longer instruction prompt (sparkles button) that frames the model as an assistant carrying out the user's order; an unedited old default is upgraded, an edited prompt stays.
* **Gboard:** T-menu providers are chosen in a modal with checkboxes; fal.ai is hidden by default unless chosen explicitly.

# 3.11.83 (2026-10-06)

Reply on screen (toolbar R), header rebind on language switch

### Changes

* **Gboard:** New toolbar tool R (filled speech bubble with a cut-out R): system screen capture consent (MediaProjection, whole display), one JPEG frame, projection stopped at once. When the keyboard is back, the spoken hint is recorded with the configured transcription provider; stopping at once replies from the screenshot alone. Screenshot + hint go as an image message to the rewording provider; the reply is inserted at the cursor.
* **Gboard:** Settings: reply system prompt and optional vision model.
* **Gboard:** Manifest: capture activity, mediaProjection foreground service and FOREGROUND_SERVICE_MEDIA_PROJECTION.
* **Gboard:** A language switch during a recording rebuilds the native header strip.

# 3.11.82 (2026-10-06)

Reasoning effort for rewording, GPT-6 models, default transcription prompts

### Changes

* **Gboard:** New "Denkaufwand" setting (none by default, low, medium, high, model default). reasoning_effort is sent only to GPT-5/GPT-6/o models and Groq gpt-oss; "none" maps to the lowest value each model accepts. A 400 reply is retried once without the parameter.
* **Gboard:** OpenAI models: GPT-6 Sol, GPT-6 Luna, GPT-6 Astra, GPT-6.1 Sol.
* **Gboard:** German and English transcription prompts are seeded once with short Whisper style samples (Whisper imitates style, max. 224 tokens).

# 3.11.81 (2026-10-06)

Rename the spoken-instruction menu back to Instant Prompting

# 3.11.80 (2026-10-06)

Idle microphone 10 % larger

# 3.11.79 (2026-10-06)

Per-language transcription prompts, replacement trace

### Changes

* **Gboard:** Transcription prompt per language (submenu "Transkriptions-Prompts": German, English, general), chosen by the language code sent to the provider; an empty language prompt falls back to the general one.
* **Gboard:** "Aufnahme verworfen" hides after 765 instead of 900 ms.
* **Gboard:** New replacements_check trace per dictation: switch, rule and term counts, parse error line, text length and matched rule numbers, without search terms or dictated text.

# 3.11.77 (2026-10-06)

Sparkles icon for the instruction prompt in the recording bar

### Changes

* **Gboard:** The recording bar and the selection prompt bar show the instruction prompt as the three-sparkles icon instead of its name.
* **Gboard:** The sparkles path now lives in TurboTypeToolIcon (Kind.SPARKLES) and is shared with the Gboard toolbar icon.

# 3.11.76 (2026-10-06)

Instruction prompt with sparkles icon, ISO language codes

### Changes

* **Gboard:** New default prompt "Anweisung"/"Instruction": the dictated or selected text is the instruction to carry out. Added once at the top (German or English by system language); a deleted prompt is not added again.
* **Gboard:** Shown in the Gboard toolbar with TurboType's three-sparkles icon (Material auto_awesome, drawn as a path).
* **Gboard:** Gboard subtype to ISO 639-1 in TurboTypeSettings.isoLanguage: en-US and en-GB become en; Android's legacy iw/in/ji become he/id/yi.

# 3.11.75 (2026-10-06)

Clearer German settings, provider submenu, language trace

### Changes

* **Gboard:** Settings regrouped by importance and fully German. Transcription page: microphone and provider, model and API access, language, behaviour; rarely used blocks moved to submenus ("Anbieter im T-Menü", "Audio & Zeitlimits"). Microphone permission only shown when missing.
* **Gboard:** New submenu "Anbieterspezifische Einstellungen" with the Groq hedge and all GROQ via Backend settings.
* **Gboard:** Own page IDs moved to 101-103 so they no longer collide with the new subpages when the settings view is restored.
* **Gboard:** Trace language_resolved (setting, Gboard subtype, code sent) and transcription_language (field and value in the Groq/OpenAI request).
* **Gboard:** Remove old MPPs from patches_compiled (deleted locally).

# 3.11.74 (2026-10-06)

Generic search and replace examples

# 3.11.73 (2026-10-06)

Fix multiline crash, replacement groups and fixed spelling

### Changes

* **Gboard:** Editing the whole list (and every multiline field since 3.11.70) crashed in View.onDrawScrollBars: scrollbars were enabled on a code-built EditText without a scrollbar drawable. A thumb drawable is set first.
* **Gboard:** Search and replace: several search terms per replacement ("Krog, Krok, Croc ; GROQ") and a per-rule "fixed spelling" checkbox (bulk: third field 1, default 0) that always writes the replacement exactly as entered. Old "search ; replacement" lines stay valid.

# 3.11.72 (2026-10-06)

Export and import Turbo-Type settings

### Changes

* **Gboard:** Main page, section "Sicherung": export all Turbo-Type settings as JSON, with or without API keys and the backend token; import from a file.
* **Gboard:** Generic over the turbotype_settings store with typed values, so settings added in later versions are included without a key list.
* **Gboard:** Import merges: settings missing in the file and existing keys stay, so partial and older files work; foreign or invalid entries are skipped.

# 3.11.71 (2026-10-06)

Search and replace on transcripts

### Changes

* **Gboard:** Global switch (default on), single rules via dialog, bulk editing as "search ; replacement" per line.
* **Gboard:** Whole words only, case-insensitive, also before punctuation; the match's casing carries over (WÖRF -> VERVE, Wörf -> Verve, else as entered). One pass, longer terms first, so replacements are never replaced again.
* **Gboard:** Applied right after transcription, so rewording works on the replaced text; live providers show the replacement in the live text already.

# 3.11.70 (2026-10-06)

Live dictation continues at the cursor

### Changes

* **Gboard:** If the cursor is no longer at the segment's end, the segment is split: the shown text stays, the rest of the sentence continues at the cursor.
* **Gboard:** Prompts saved, renamed or deleted later are updated in the Gboard tool list right away (catalog refresh, mlh.g / mlh.c) instead of only after a keyboard restart.
* **Gboard:** Multiline fields in the settings dialogs (prompt instruction) show a scrollbar and scroll inside the dialog.

# 3.11.69 (2026-10-05)

Hedge over a separate Groq connection

### Changes

* **Gboard:** The second request of a hedge or race uses its own connection pool (TurboTypeHttp.SEPARATE); the Groq connection in that pool is warmed and evicted on network change like the main one.
* **Gboard:** Connection log: URL requests are "groq_url", requests on the separate pool carry "_separate".

# 3.11.68 (2026-10-05)

Hedge the direct Groq upload with the backend URL

# 3.11.67 (2026-10-05)

Hedge slow Groq requests

### Changes

* **Gboard:** Groq hedge (default 1.2 s; 0.8/1.5/2 s or off): without an answer, the same request is sent again and the faster answer wins; the other is cancelled. Applies to direct file and backend URL requests for Groq and GROQ via Backend.
* **Gboard:** The optional race of both paths uses the same first-wins helper.
* **Gboard:** Logs: leg_started, leg_finished; route_result winner=direct_hedge when the second request won.
* **Gboard:** Connection log names chat completions "rephrase" instead of deriving the stage from the host.

# 3.11.66 (2026-10-05)

Warm every provider, not just Groq

### Changes

* **Gboard:** Warm the selected transcription provider (Groq, OpenAI, Gemini, Fireworks, fal.ai), the GROQ-via-Backend server and, when rephrasing is enabled (prompt button or instant prompting), the rephrasing provider: on keyboard open, every 20 s while recording and after a network change.
* **Gboard:** Live providers stay out; they connect at recording start.
* **Gboard:** Logs: warmup target=<host>.

# 3.11.65 (2026-10-05)

Forget upload failures from the previous network

# 3.11.64 (2026-10-05)

Reconnect when the network changes

### Changes

* **Gboard:** Watch the default network. On a switch, or when a network returns after a dead zone, evict the Groq and backend connection pools and re-warm both right away while recording or within 5 minutes of the keyboard opening.
* **Gboard:** A running backend upload cancels the request stuck on the old network and retries immediately; this does not count as an upload failure for the route decision.
* **Gboard:** Logs: network_changed, network_lost, backend_network_switch, warmup trigger=network.

# 3.11.63 (2026-10-05)

Do not underestimate the cellular uplink

### Changes

* **Gboard:** Use the larger of the chunk measurement and half of Android's uplink estimate; the example now predicts ~450 ms direct vs ~640 ms backend.
* **Gboard:** Log the chunk measurement separately (measuredUpKbps, TSV column MEASURED_UP_KBPS).

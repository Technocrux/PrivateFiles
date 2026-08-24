# Privacy Policy

**WhisperFlow — AI voice dictation**

Publisher: Technocrux  
Last updated: 19 August 2026  
Applies to: WhisperFlow for Windows, version 1.0.0 and later

---

## The short version

WhisperFlow turns speech into text entirely on your own computer. Your voice is never
uploaded, never sent to a server, and never used to train anything. There is no
account to create and no sign-in. WhisperFlow does not collect analytics, telemetry,
crash reports or usage statistics of any kind.

The only network requests WhisperFlow ever makes are to download the speech engine and
speech model files you choose to install, and those downloads carry nothing
about you beyond what any file download necessarily reveals to the host serving
it.

---

## 1. What WhisperFlow processes, and why

### 1.1 Your voice

While you hold (or have latched) the dictation key, WhisperFlow records audio from the
microphone you selected. Recording stops the moment the key is released or
tapped again. WhisperFlow does not listen at any other time, and there is no
wake-word, always-on, or background listening mode.

That audio is transcribed **on your computer** by a local speech engine
(whisper.cpp) running as a process on your machine.

- When the resident speech engine is running, the audio is held in memory and
  passed to it over a connection to `127.0.0.1` — your own machine, which never
  reaches the network.
- When WhisperFlow falls back to the command-line engine, the audio is written to a
  temporary `.wav` file in your system temporary folder, read by the engine,
  and deleted immediately afterwards.

Audio is never retained after a dictation completes, and is never transmitted
off your device.

### 1.2 The text WhisperFlow produces

The transcript is cleaned up using fixed, built-in rules that run locally.
There is no language model and no cloud service involved in this step.

The finished text is delivered to whichever application had focus, using the
clipboard or simulated keystrokes according to your settings.

### 1.3 Dictation history

If **Save history** is enabled (it is on by default), WhisperFlow stores a record of
each dictation on your computer so you can find and reuse what you have said.
Each record contains:

- the finished text and the raw transcript,
- how long you spoke and the word count,
- the name of the application and the title of the window the text was sent to,
- which engine and model transcribed it, and how long that took.

This is stored **only** in a file on your computer, at
`%APPDATA%\WhisperFlow\flow-data.json`. It is never uploaded.

Window titles can contain sensitive information — a document name, a customer
name, the subject of an email. If you would rather WhisperFlow did not keep any of
this, turn **Save history** off in Settings; nothing is written from then on.
You can also delete individual entries or clear the history at any time.

### 1.4 Keyboard input

To offer hold-to-talk in every application, WhisperFlow installs a system-wide
keyboard hook. This is the only way Windows allows a program to detect a key
being held while another application has focus.

WhisperFlow inspects each key event solely to decide whether it is part of your chosen
dictation key. Keystrokes are **not** recorded, stored, logged or transmitted.
The one other use is safety: while WhisperFlow is typing text for you, a key press
that is not the dictation key tells WhisperFlow that you have taken over, so it stops
editing text it no longer owns.

### 1.5 The clipboard

When WhisperFlow inserts text by pasting, it briefly places that text on your
clipboard. Depending on your settings, it either leaves the text there for you
or restores your previous clipboard contents afterwards. WhisperFlow does not read,
retain or transmit clipboard contents for any other purpose.

### 1.6 Application and window information

To choose sensible formatting and to record where a dictation went, WhisperFlow reads
the title of the focused window and the name of the process that owns it. This
information stays on your device and is used only as described in section 1.3.

### 1.7 Your dictionary and snippets

Words, names and shortcuts you add are stored in the same local data file and
used to improve transcription accuracy. They are never uploaded.

---

## 2. What leaves your device

WhisperFlow makes network requests in exactly one situation: when you choose to
download or update the local speech engine or a speech model. Those requests go
to:

- **GitHub** (`github.com`), for the whisper.cpp runtime, and
- **Hugging Face** (`huggingface.co`), for the speech model files.

These are ordinary file downloads. WhisperFlow sends no account information, no
identifier, and no content of any kind with them. The operators of those
services will see the request in their own logs, as they would for any
download, subject to their own privacy policies.

WhisperFlow contains no advertising, no analytics SDK, no crash reporting service and
no update-checking beacon.

---

## 3. Where your data lives

| What | Where |
| --- | --- |
| Settings, history, dictionary, snippets | `%APPDATA%\WhisperFlow\flow-data.json` |
| Speech engine and model files | `%APPDATA%\WhisperFlow\engines\` |
| Temporary audio (command-line engine only) | System temp folder, deleted after use |

All of it is on your computer, under your Windows user account, and subject to
whatever backup or sync you have configured yourself.

---

## 4. How long it is kept

- **Audio** — for the duration of the transcription only.
- **History** — until you delete it, or until it passes the history limit you
  set (1,000 entries by default), at which point the oldest entries are dropped.
- **Settings, dictionary, snippets** — until you change or remove them.

Uninstalling WhisperFlow does not delete your data file by default, so that
reinstalling restores your settings. To remove everything, delete the
`%APPDATA%\WhisperFlow` folder.

---

## 5. Your control

Because everything is local, you exercise your rights directly rather than by
asking us:

- **Access** — open `%APPDATA%\WhisperFlow\flow-data.json`; it is plain, readable JSON.
- **Deletion** — clear the history in Settings, or delete the folder.
- **Restriction** — turn off **Save history** to stop new records being kept.
- **Portability** — copy the file.

Where the GDPR, UK GDPR, CCPA/CPRA or similar laws apply, note that
Technocrux does not receive, store or process your personal data
from WhisperFlow at all, and therefore holds nothing to disclose, correct, port or
delete. We do not sell or share personal information, because we never receive
any.

---

## 6. Permissions WhisperFlow requests

| Permission | Why |
| --- | --- |
| Microphone | To hear you while the dictation key is held |
| Keyboard hook | To detect the dictation key in any application |
| Simulated input / UI Access | To type or paste the finished text into the app you were using |
| Network | Only to download the speech engine and models you choose |

WhisperFlow's signed release runs with the Windows **UI Access** privilege. This is the
same accessibility mechanism used by screen readers and on-screen keyboards. It
allows WhisperFlow to type into applications that are running as administrator, which
Windows otherwise blocks. It does **not** grant WhisperFlow administrator rights and
does not let it read the contents of other applications.

---

## 7. Children

WhisperFlow is a general-purpose productivity tool and is not directed at children
under 13. It collects nothing from anyone, of any age.

---

## 8. Security

WhisperFlow's release build is Authenticode-signed, so Windows can verify it has not
been tampered with. Because your dictation data never leaves your machine,
protecting it is a matter of protecting your Windows account: use a password or
Windows Hello, and enable disk encryption if the content is sensitive.

---

## 9. Changes to this policy

If this policy changes, the updated version will be published at
[Privacy Policy URL] with a new "Last updated" date. Material changes to what
WhisperFlow does with your data will also be described in the release notes for the
version that introduces them.

---

## 10. Contact

Questions about this policy, or about privacy in WhisperFlow:

**Technocrux**  
[Contact Email]  
[Postal Address, if required by your jurisdiction]

---

### Before you publish

Replace every bracketed placeholder above: `Technocrux`,
`[Contact Email]`, `[Postal Address...]` and `[Privacy Policy URL]`. Partner
Center requires a publicly reachable privacy policy URL; host the generated
`store/legal/privacy.html`, or your own copy of this text, at a stable address.

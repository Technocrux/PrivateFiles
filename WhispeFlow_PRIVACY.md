# Privacy Policy

**WhisperFlow — AI voice dictation**

Publisher: Technocrux  
Last updated: 24 August 2026  
Applies to: WhisperFlow for Windows, version 1.0.0 and later

---

## The short version

WhisperFlow turns speech into text entirely on your own computer. Your voice is
never uploaded, never sent to a server, and never used to train anything.

WhisperFlow does need a WhisperFlow account. You sign in with an email address
and a password, and that account exists for two reasons only: to carry your
settings, dictionary and snippets between the computers you use, and to hold
your subscription. It is not used to profile you, and it is not shared with
anyone.

**Your voice, your transcripts and your dictation history never leave your
computer.** They are not synced, we hold no copy of them, and we cannot read
them. WhisperFlow contains no analytics, no telemetry, no crash reporting, no
advertising and no tracking of any kind.

---

## 1. What WhisperFlow processes on your computer

### 1.1 Your voice

While you hold (or have latched) the dictation key, WhisperFlow records audio
from the microphone you selected. Recording stops the moment the key is released
or tapped again. WhisperFlow does not listen at any other time, and there is no
wake-word, always-on, or background listening mode.

That audio is transcribed **on your computer** by a local speech engine
(whisper.cpp) running as a process on your machine.

- When the resident speech engine is running, the audio is held in memory and
  passed to it over a connection to `127.0.0.1` — your own machine, which never
  reaches the network.
- When WhisperFlow falls back to the command-line engine, the audio is written to
  a temporary `.wav` file in your system temporary folder, read by the engine,
  and deleted immediately afterwards.

Audio is never retained after a dictation completes, and is never transmitted off
your device.

### 1.2 The text WhisperFlow produces

The transcript is cleaned up using fixed, built-in rules that run locally. There
is no language model and no cloud service involved in this step.

The finished text is delivered to whichever application had focus, using the
clipboard or simulated keystrokes according to your settings.

### 1.3 Dictation history

If **Save history** is enabled (it is on by default), WhisperFlow stores a record
of each dictation on your computer so you can find and reuse what you have said.
Each record contains:

- the finished text and the raw transcript,
- how long you spoke and the word count,
- the name of the application and the title of the window the text was sent to,
- which engine and model transcribed it, and how long that took.

This is stored **only** in a file on your computer, at
`%APPDATA%\WhisperFlow\flow-data.json`. **History is never synced to your
account and is never uploaded**, even when cloud sync is switched on — see
section 3.

Window titles can contain sensitive information — a document name, a customer
name, the subject of an email. If you would rather WhisperFlow did not keep any
of this, turn **Save history** off in Settings; nothing is written from then on.
You can also delete individual entries or clear the history at any time.

### 1.4 Keyboard input

To offer hold-to-talk in every application, WhisperFlow installs a system-wide
keyboard hook. This is the only way Windows allows a program to detect a key
being held while another application has focus.

WhisperFlow inspects each key event solely to decide whether it is part of your
chosen dictation key. Keystrokes are **not** recorded, stored, logged or
transmitted. The one other use is safety: while WhisperFlow is typing text for
you, a key press that is not the dictation key tells WhisperFlow that you have
taken over, so it stops editing text it no longer owns.

### 1.5 The clipboard

When WhisperFlow inserts text by pasting, it briefly places that text on your
clipboard. Depending on your settings, it either leaves the text there for you or
restores your previous clipboard contents afterwards. WhisperFlow does not read,
retain or transmit clipboard contents for any other purpose.

### 1.6 Application and window information

To choose sensible formatting and to record where a dictation went, WhisperFlow
reads the title and the owning process of the focused window. This information
stays on your device and is used only as described in section 1.3.

### 1.7 Your dictionary and snippets

Words, names and shortcuts you add are stored in the local data file and used to
improve transcription accuracy. Unlike your history, these **are** synced to your
account so they follow you between machines. Section 3 explains exactly what that
means, and how to think about what you put in them.

### 1.8 Usage statistics

WhisperFlow keeps a local count of words dictated, time spent speaking and a
per-day summary, so it can show you your own totals. These counters stay on your
computer. They are not synced and are not sent anywhere.

---

## 2. Your account

Using WhisperFlow requires an account. Accounts are operated by Technocrux
through the WhisperFlow account service at `https://flyo.azurewebsites.net`.

### 2.1 What you give us

| Data | When | Why |
| --- | --- | --- |
| Email address | Registration | Identifies the account, verifies it, and is used for verification and password-reset messages |
| Password | Registration | Authentication. It is transmitted over TLS and stored by the service only in hashed form; we never see it in the clear |
| Display name | Optional, in Settings | Shown in the app |
| Profile picture | Optional, in Settings | Shown in the app. It is re-encoded to a small square PNG on your machine before upload |
| Two-factor secret and recovery codes | Only if you enable 2FA | Protects the account |

### 2.2 What the service records about your use of it

- An account identifier and a **device identifier** — a random value generated on
  first run, tied to the installation and not to your hardware, your Windows
  account or you personally.
- A record of each active sign-in session: when it was issued, the device
  identifier and a device description (for example "WhisperFlow on WORKSTATION"),
  so you can see and revoke your own sessions.
- Ordinary server request logs, which necessarily include your IP address and
  timestamps. These are used to operate and secure the service — rate limiting,
  abuse prevention, diagnosing faults — and for nothing else.

### 2.3 How sign-in is stored on your computer

Your sign-in tokens are written to `%APPDATA%\WhisperFlow\account.json`,
encrypted with Windows DPAPI through Electron's `safeStorage`, so they are
readable only by your Windows user account on that machine. They are kept
deliberately apart from `flow-data.json`, so that exporting or resetting your
WhisperFlow data neither carries away nor destroys your session.

Refresh tokens rotate on every use. Because a signed-in session is remembered on
disk, WhisperFlow keeps working offline indefinitely once you have signed in; only
a brand-new installation needs the network to get past sign-in.

### 2.4 Legal basis

Where the GDPR or UK GDPR applies, we process this account data to perform our
contract with you (providing the application, sync and your subscription), and on
the basis of our legitimate interest in keeping the service secure and available.
We do not use it for marketing, and we do not profile you.

---

## 3. Cloud sync — what travels, and what never does

When you are signed in, WhisperFlow keeps a small number of things in step across
your machines. The list is an allowlist: anything not named here is not sent,
including anything added to the app in future until this policy says otherwise.

| Synced to your account | Never synced |
| --- | --- |
| App settings that describe *how* you dictate: hotkey, tone, language, punctuation and filler options, paste and clipboard behaviour, overlay position, sounds, whether history is saved and its limit | Audio, transcripts and dictation history |
| Your dictionary entries | Your usage statistics and word counts |
| Your snippets | Microphone choice, speech model and engine choice, file paths, launch-at-login and other device-specific settings |
| Your display name and profile picture | Anything about which applications you dictate into |

Two details worth stating plainly:

- **Deletions travel as tombstones.** When you delete a dictionary entry or a
  snippet, the account records a small marker saying that entry was deleted, so
  your other machine does not restore it. The marker holds the entry's identifier
  and the time of deletion, not its content, and is discarded once every device
  has seen it.
- **Your dictionary and snippets are content you choose.** They are stored on our
  service so they can reach your other computers. Treat them as you would any
  cloud-stored note: they are the one part of WhisperFlow where what you type is
  held by us.

All traffic to the account service uses HTTPS. Sync data is stored per account and
is never combined across accounts, sold, shared or used to train anything.

---

## 4. Subscriptions and payment

WhisperFlow is free for 7 days from first run, and needs a subscription after
that. In the Microsoft Store build:

- The purchase is made through the **Microsoft Store**. Microsoft is the
  merchant. **We never see or receive your card details, billing address or
  payment identifiers.**
- WhisperFlow asks Windows whether your account holds a valid licence, and caches
  the answer locally so the app keeps working when the Store is unreachable.
- The 7-day trial is recorded as a timestamp in your local data file. Nothing
  about the trial is reported to us.

Microsoft's own privacy statement covers the purchase itself.

---

## 5. What leaves your device

WhisperFlow makes network requests in exactly four situations:

| To | When | What is sent |
| --- | --- | --- |
| The WhisperFlow account service (`flyo.azurewebsites.net`) | Signing in, and while syncing | Your account credentials or session token, and the synced items listed in section 3 |
| **GitHub** (`github.com`) | You choose to install or update the speech engine | Nothing but the file request itself |
| **Hugging Face** (`huggingface.co`) | You choose to download a speech model | Nothing but the file request itself |
| **Microsoft Store** | Checking or buying your subscription | Handled by Windows; we receive only whether a licence exists |

The engine and model downloads are ordinary file downloads. WhisperFlow sends no
account information, no identifier and no content of any kind with them. The
operators of those services will see the request in their own logs, as they would
for any download, subject to their own privacy policies.

WhisperFlow contains no advertising, no analytics SDK, no crash reporting service
and no update-checking beacon.

---

## 6. Where your data lives

| What | Where |
| --- | --- |
| Settings, history, statistics, dictionary, snippets | `%APPDATA%\WhisperFlow\flow-data.json` (your computer) |
| Sign-in tokens and device identifier | `%APPDATA%\WhisperFlow\account.json`, encrypted (your computer) |
| Speech engine and model files | `%APPDATA%\WhisperFlow\engines\` (your computer) |
| Cached profile picture | `%APPDATA%\WhisperFlow\` (your computer) |
| Temporary audio (command-line engine only) | System temp folder, deleted after use |
| Account, synced settings, dictionary, snippets, profile | The WhisperFlow account service |

Everything on your computer sits under your Windows user account, and is subject
to whatever backup or sync you have configured yourself.

---

## 7. How long it is kept

- **Audio** — for the duration of the transcription only.
- **History** — until you delete it, or until it passes the history limit you set
  (1,000 entries by default), at which point the oldest entries are dropped.
- **Settings, dictionary, snippets** — until you change or remove them. Removing
  one while signed in removes it from your account too.
- **Account data** — until you delete your account.
- **Sessions** — until they expire or you revoke them, from Settings → Account.
- **Server logs** — kept only as long as needed to operate and secure the
  service.

Uninstalling WhisperFlow does not delete your local data file by default, so that
reinstalling restores your settings. To remove everything on the machine, delete
the `%APPDATA%\WhisperFlow` folder.

---

## 8. Your control and your rights

Most of your data is local, so you exercise most of your rights directly:

- **Access** — open `%APPDATA%\WhisperFlow\flow-data.json`; it is plain, readable
  JSON. Settings → About also exports it.
- **Deletion** — clear the history in Settings, or delete the folder.
- **Restriction** — turn off **Save history** to stop new records being kept.
- **Portability** — copy the file.

For the account data we do hold:

- **See and correct it** — Settings → Account.
- **Sign out everywhere** — revokes every session on every device.
- **Delete it** — Settings → Account → delete account. This removes your email
  address, profile, and the settings, dictionary and snippets held for you on the
  service. It does not touch the copy on your computer, which stays yours.
- **Ask us** — write to the address in section 13 for any request under the GDPR,
  UK GDPR, CCPA/CPRA or a comparable law.

We do not sell personal information, and we do not share it for cross-context
behavioural advertising. Your voice, transcripts and history are not ours to
disclose, correct, port or delete, because we never receive them.

---

## 9. Permissions WhisperFlow requests

| Permission | Why |
| --- | --- |
| Microphone | To hear you while the dictation key is held |
| Keyboard hook | To detect the dictation key in any application |
| Simulated input / UI Access | To type or paste the finished text into the app you were using |
| Network | Your account and sync, and the speech engine and models you choose to download |

The signed installer release of WhisperFlow runs with the Windows **UI Access**
privilege. This is the same accessibility mechanism used by screen readers and
on-screen keyboards, and it allows WhisperFlow to type into applications running
as administrator, which Windows otherwise blocks. It does **not** grant
WhisperFlow administrator rights and does not let it read the contents of other
applications. The Microsoft Store build cannot hold this privilege, so in that
build dictation into elevated applications is unavailable and WhisperFlow says so
plainly.

---

## 10. Children

WhisperFlow is a general-purpose productivity tool and is not directed at
children. Because an account is required, you must be at least 13 years old — or
older, where the law where you live sets a higher age for consenting to online
services — to use it.

---

## 11. Security

- Traffic to the account service is encrypted with HTTPS.
- Sign-in tokens are encrypted at rest on your machine with Windows DPAPI, and
  refresh tokens rotate on every use, so a stolen token is detectable and short-
  lived.
- Optional two-factor authentication and recovery codes are available in
  Settings → Account.
- The release build is Authenticode-signed, so Windows can verify it has not been
  tampered with.

No service can promise perfect security. Because your dictation content never
leaves your machine, protecting it is mostly a matter of protecting your Windows
account: use a password or Windows Hello, and enable disk encryption if the
content is sensitive.

---

## 12. Changes to this policy

If this policy changes, the updated version will be published at
[the WhisperFlow privacy policy page](https://github.com/Technocrux/cutepets/blob/main/PRIVACY-POLICY.md)
with a new "Last updated" date. Material changes to what WhisperFlow does with
your data will also be described in the release notes for the version that
introduces them.

---

## 13. Contact

Questions about this policy, or about privacy in WhisperFlow:

**Technocrux**  
alisufyanbutt@hotmail.com

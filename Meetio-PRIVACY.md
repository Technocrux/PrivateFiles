# Privacy Policy — Meetio

**Publisher:** Technocrux
**Application:** Meetio — AI based meetings (Microsoft Store)
**Support:** alisufyanbutt@live.com
**Last updated:** 6 September 2026

---

## The short version

Meetio records, transcribes and summarises meetings **on your own PC**. Your
audio, your transcripts and your summaries are stored on your device and are
never uploaded to Technocrux or to anyone else.

The app uses the network for four things only: signing you in, downloading the AI
models, syncing your account settings, and — if you ask it to — sending a
follow-up email you have written and reviewed.

We do not sell your data. We do not use your meetings to train AI models.

---

## 1. What stays on your device

All of the following is written to your PC and never leaves it:

| Data | Where it lives |
|---|---|
| Meeting audio recordings | Local app data folder |
| Transcripts, including speaker labels | Local SQLite database |
| Summaries, key points, decisions | Local SQLite database |
| Action items and their owners | Local SQLite database |
| Draft follow-up emails | Local SQLite database |
| Downloaded AI models | Local app data folder |
| Your model and capture preferences | Local SQLite database |

Speech recognition (Whisper) and summarisation (Phi-3.5) run as local processes
on your CPU or GPU. No third-party AI provider, API key or cloud inference
service is involved at any point.

Once the models are installed, Meetio's core function works with the network
disconnected.

**Location:** for a Microsoft Store installation this data is under
`%LOCALAPPDATA%\Packages\65490Technocrux.Meetio-AIbasedmeetings_<id>\LocalCache\Local\Meetio\`.

---

## 2. What we do collect

### 2.1 Account information

To create and use an account we process:

- **Email address** — your identifier, and the address used for password reset.
- **Display name**, if you provide one.
- **A hash of your password.** We never store or transmit your password in plain
  text.
- **Session tokens**, so you are not asked to sign in on every launch.
- **The date your free trial started**, so the seven-day trial cannot be reset by
  reinstalling.
- **A count of meetings processed**, as a number only. We do not receive their
  titles, contents, durations or participants.

This is held by **Flyo**, the authentication and settings service Technocrux
operates for its applications. It is transmitted over HTTPS.

### 2.2 Your account settings

Non-content preferences (theme, chosen model, capture defaults) are synced so the
app behaves the same on each of your devices. Meeting content is never part of
this sync.

### 2.3 Purchases

Subscriptions are sold and billed **by the Microsoft Store**, not by Technocrux.
Microsoft tells the app only whether an active subscription is held. **We never
see your card number, billing address or payment method.** Microsoft's handling
of that data is governed by the Microsoft Privacy Statement.

### 2.4 Model downloads

AI models are downloaded from Hugging Face and GitHub. Those requests carry your
IP address to those providers as any web request would. They contain no account
identifier and no meeting data.

### 2.5 Crash and diagnostic logs

Diagnostic logs are written **locally** and are not transmitted automatically. If
you choose to send a log to support, you are sending it deliberately and by
email. Logs record errors and app events; they do not contain meeting audio or
transcript text.

---

## 3. Email sending

If you use **Send follow-up email**, the message you have reviewed is delivered
through **Azure Communication Services**, which acts as our processor purely to
transmit it. The recipients and body are the ones you chose. Only that message is
transmitted — no other meeting content is included, and no copy is retained by us
beyond what the delivery service requires to send it.

You are never required to use this feature. Copying the draft and sending it from
your own mail client keeps the content entirely local.

---

## 4. What we never do

- We never upload your meeting audio, transcripts or summaries.
- We never use your meetings to train any AI model, ours or anyone else's.
- We never sell, rent or share your personal data with advertisers or data
  brokers.
- We do not embed advertising or third-party analytics SDKs.
- We do not track you across other apps or websites.

---

## 5. Recording other people

Meetio records audio at your instruction. **You are responsible for having the
consent or legal basis required to record any meeting**, which in many
jurisdictions means telling every participant. Technocrux cannot obtain that
consent for you. Please check the rules that apply where you and the other
participants are.

---

## 6. Retention

- **On your device:** meetings are kept until you delete them. Uninstalling
  Meetio removes the local database and recordings.
- **Account data:** kept while your account exists. Delete your account from
  **Settings → Account → Delete account**, or by writing to
  alisufyanbutt@live.com, and we erase your account record and settings within
  30 days. Because your meeting content was never sent to us, there is nothing
  of it for us to delete.

---

## 7. Your rights

Depending on where you live — including under the UK GDPR, the EU GDPR and the
CCPA — you may have the right to access, correct, export or delete the personal
data we hold, to object to or restrict its processing, and to withdraw consent.

Since the only personal data we hold is your account record, these requests are
straightforward. Write to **alisufyanbutt@live.com** and we will respond within
30 days. You also have the right to complain to your local data protection
authority.

---

## 8. Children

Meetio is not directed at children under 13, and we do not knowingly collect
their personal data. If you believe a child has created an account, contact us
and we will remove it.

---

## 9. Security

Account traffic uses HTTPS. Passwords are hashed, never stored in plain text.
Session tokens on your PC are protected with the Windows Data Protection API
(DPAPI), so they are readable only by your Windows user account. Refresh tokens
are single-use: if one is replayed, the whole token family is revoked and you are
signed out — a deliberate trade of convenience for safety.

No system is perfect. If you find a vulnerability, please report it to
alisufyanbutt@live.com rather than disclosing it publicly, and we will work with
you on a fix.

---

## 10. International transfers

Our authentication and email infrastructure runs on Microsoft Azure and may
process your account data in a region other than your own. Where required, such
transfers rely on the Standard Contractual Clauses. Your meeting content is not
transferred anywhere, because it never leaves your PC.

---

## 11. Changes

If we change this policy materially we will update the date above and note the
change in the app's release notes. Continuing to use Meetio after a change means
you accept the revised policy.

---

## 12. Contact

**Technocrux**
Email: **alisufyanbutt@live.com**

For anything about this policy, a data request, or a security report, that
address reaches us directly.

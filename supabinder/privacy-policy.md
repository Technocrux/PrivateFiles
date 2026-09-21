# Privacy Policy — SupaBinder

**Publisher:** Technocrux
**Company:** Devride.com
**Last updated:** 21 September 2026

---

## 1. Summary

SupaBinder stores your documents **on your device only**. We do not upload,
read, sell, or share them. We do not use advertising, and we do not use
analytics or tracking.

If you choose to create an account, the only information that leaves your
device is your email address, an optional display name, and the password you
set — used solely to sign you in.

---

## 2. What stays on your device

Everything you put into SupaBinder is held locally in encrypted storage:

- Photographs, scans and PDF documents you capture or import
- Text recognised from those documents
- Item titles, notes, prices, dates, serial and model numbers
- Binders, sub-binders and how you have organised them
- Contacts you add or that are read from a receipt
- Warranty dates and reminders
- Search indexes built from the above
- App settings, including your chosen currency and theme

**None of this is transmitted to us or to anyone else.** It is not backed up
to our servers, because we operate no servers for it.

---

## 3. How your data is protected

- The database is encrypted with **AES-256** (SQLite3MultipleCiphers).
- Every document is separately sealed with **AES-256-GCM**.
- The encryption key is generated on your device and held in the **Android
  Keystore**, backed by hardware security where your device provides it. The
  key never leaves the device and is not known to us.
- Optional app lock using your fingerprint, face or device screen lock.
- Optional per-binder PIN. The PIN itself is never stored — only an Argon2id
  hash of it, with a random salt, in the same Keystore-backed storage as the
  encryption keys. It is checked on your device and is never transmitted. We
  cannot recover or reset it.
- Optional blocking of screenshots and of the app's preview in the recent-apps
  switcher.

Because the key is device-bound, **we cannot recover your documents** if you
lose the device or uninstall the app. This is a deliberate consequence of the
design. Use the backup feature described in section 6.

---

## 4. Processing that happens on your device

The following run entirely on your phone. No image, no recognised text, and no
document is sent anywhere for processing:

- **Document scanning** — edge detection, perspective correction and image
  clean-up.
- **Text recognition (OCR)** — reading text from your photographs.
- **Receipt parsing** — identifying merchant, date, total, currency, phone
  numbers and serial numbers from recognised text.
- **Image quality checks** — blur detection and duplicate-page detection.
- **Search** — both keyword and similarity search are computed locally.
- **Lighting checks** — the phone's ambient light sensor is read while you are
  capturing, to decide whether to switch the camera flash on. It reports how
  bright the room is; it is not a camera and it records nothing. Captured pages
  are also measured for darkness and shadow, on the device, to warn you if a
  page came out hard to read.

The text-recognition component is provided by Google ML Kit and runs offline.
The first time you scan, your device may download the recognition model from
Google Play Services. That download is a request to Google for a model file;
**none of your content is included in it.**

---

## 5. Account information

Accounts are optional. If you create one, we process:

| Data | Why | Retention |
|---|---|---|
| Email address | Sign-in, account recovery | Until you delete the account |
| Display name (optional) | Shown in the app | Until you delete the account |
| Password | Stored only as a cryptographic hash; we never see the original | Until you delete the account |
| Device name and a random device identifier | So you can see and revoke your signed-in devices | Until the session is revoked |
| Sign-in timestamps | Security and abuse prevention | Until you delete the account |

Authentication is provided by our own service. Your documents are **never**
sent to it.

**Deleting your account.** You may delete your account from within the app.
Deletion is scheduled with a 30-day grace period, during which signing in
again cancels it. After that period the account and its data are removed.
Deleting your account does not delete the documents on your device, and
deleting the app does not delete your account.

---

## 6. Backups you create

You can export an encrypted backup of your vault. The backup is sealed with a
passphrase **you choose**, using Argon2id key derivation and AES-256-GCM.

### What a backup contains

One `.supabinder` file holding everything needed to rebuild your vault on
another phone:

- Every document you have captured or imported
- Every item, binder, contact, link and reminder
- The key that unwraps your documents, so they are readable on the new phone
- Your app settings, and your binder PIN **as a cryptographic hash** — never
  the PIN itself

Everything in that list sits inside the encrypted payload. Only the file's
short header — the date, the number of items, and the parameters needed to
derive the key from your passphrase — is readable without it.

A backup deliberately does **not** contain your account credentials, your
sign-in session, or the identifier of the device that wrote it.

### Where it goes

You decide. **We never receive it**, and the app has no destination of its own.

- **Save or share it manually.** The file is handed to whichever app you pick.
- **Automatic backups.** You choose a folder once, using Android's own folder
  picker. The app is granted access to that folder and nothing else, writes
  each backup there, and removes its own older backups to the limit you set. It
  never reads anything else in that folder. You can withdraw the access at any
  time, in the app or in Android's settings.
- **Google Drive.** If you have the Drive app installed, one tap hands a
  finished backup to it. SupaBinder does not sign in to Drive, does not ask for
  access to your Drive account, and cannot see what is in it. It passes the app
  a file, in the same way you would share any other file.

Once the file reaches a destination, that destination's own privacy policy
applies to it.

We cannot recover your backup passphrase. If you lose it, the backup cannot be
opened by anyone, including us.

---

## 7. Permissions the app requests

| Permission | Why | Optional |
|---|---|---|
| Camera | Photographing and scanning documents | Yes — you can import files instead |
| Internet | Sign-in only, and the one-time model download | Yes, if you do not use an account |
| Biometrics | App lock, if you enable it | Yes |
| Notifications | Warranty and expiry reminders | Yes |
| Run at startup | Restoring your scheduled reminders after a restart | Yes |
| Read images | Importing a photo you pick from your gallery | Yes |
| Vibrate | Haptic feedback on capture and unlock | Yes |

The camera permission also covers switching the **flash** on while you are
photographing a document in a dark room. The **ambient light sensor** needs no
permission and is only read during a capture.

Access to a folder for automatic backups is not an app permission: it is
granted per folder, by you, through Android's own picker, and revoked the same
way.

We do not request location, contacts or microphone. The camera and picker
libraries the app is built on declare a microphone permission by default
because they are also capable of recording video; SupaBinder removes it from
the app at build time, so it does not appear on the app's Play listing and
cannot be granted.

Network country is read from the mobile network to choose your default
currency. This needs no permission, is a country code only, and never leaves
the device.

---

## 8. Sharing

The app never transmits your documents on its own. A document leaves the app
only when **you** tap share and choose a destination. At that point it is
handed to the app you selected, and that app's own privacy policy applies.

We do not sell personal information. We do not share it with advertisers. We
have no advertising or analytics software in the app.

---

## 9. Children

SupaBinder is not directed at children under 13 and we do not knowingly
collect information from them.

---

## 10. Your rights

Depending on where you live, you may have the right to access, correct, export
or delete the personal information we hold, and to object to or restrict its
processing.

In practice: your documents are already entirely in your possession and can be
exported at any time. For account information, deletion is available in the
app. For anything else, contact us.

---

## 11. Changes

If this policy changes materially we will update the "last updated" date above
and note the change in the app's release notes.

---

## 12. Contact

Technocrux — Devride.com

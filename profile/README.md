<h1 align="center">OmniVerbis</h1>

<p align="center">
  <strong>Live speech and document translation for events, conversations and phone calls.</strong>
</p>

<p align="center">
  <a href="https://omniverbis.com">omniverbis.com</a>
</p>

---

Translation is usually something you arrange in advance — an interpreter booth, a translated
PDF, a bilingual colleague on the call. **OmniVerbis** makes it something you switch on: speak
into any phone or feed, and every listener reads or hears it in their own language a second
later. Nothing is recorded; audio and transcripts live only in memory while someone is talking.

### What it does

- **Events and conferences** — the organizer creates an event and gets a QR code (or a stable
  vanity code for recurring events). The audience scans it, picks a language, and reads or
  listens to the live translation on their own phone. The audio source is the broadcaster page
  on any phone near the speaker, or anything ffmpeg can read — mixer feed, RTMP/OBS, Dante —
  over the channel API.
- **Conversation mode** — two people, two languages, one phone on the table. Speech direction
  is auto-detected; each side of the flipped screen shows the dialogue in its language,
  optionally spoken aloud.
- **Phone interpreter** — call from a plain mobile; a number in the middle interprets both
  directions live, with the original voice ducked under the translation and a disclosure to
  both sides.
- **Document translation** — upload a PDF or photo; OCR, translation and a certified bilingual
  `.docx` come back, with workspaces to manage the batch.
- **Native mobile app** — iOS and Android with full parity to the web app; the microphone keeps
  broadcasting with the screen locked.
- **Pluggable backends** — Google Cloud Speech-to-Text + Translation with Gemini-contextualised
  finals by default, Gemini Live speech-to-speech in production, and an archived fully
  self-hosted Whisper + NLLB pipeline for on-prem deployments.

### Repositories

Everything here is private — the platform ships from separate repos, one deployable each,
tied together by a workspace repo that Claude Code and the team work from.

| Repo | |
| --- | --- |
| **workspace** | The workspace: shared `CLAUDE.md`, scripts, sprint board — clone this one first, it pulls the rest |
| **server** | NestJS API + socket.io — auth, events, translation providers, document pipeline, phone interpreter (`api.omniverbis.com`) |
| **web** | Next.js app — broadcaster, listener, conversation, documents, admin (`omniverbis.com`) |
| **mobile** | Expo native app for iOS and Android, full parity with the web app (EAS builds) |
| **docs** | Docusaurus product guide + engineering reference |
| **ml-service** | Archived self-hosted ASR/MT provider (Silero VAD → faster-whisper → NLLB, CUDA) |

### Contact

For anything about the platform: **[omniverbis.com](https://omniverbis.com)**.

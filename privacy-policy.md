# Privacy Policy — Session Helper

**Last updated:** 2026-04-02

**Data controller:** Session Helper LLC, New Mexico

## What This Bot Does

The Session Helper Bot ("the Bot") records tabletop RPG voice sessions in Discord for the Open Voice Project, a community-contributed audio dataset for speech research and transcription. Recorded audio is licensed according to each participant's chosen restrictions (see "Licensing Model" below).

## What Data We Collect

### Audio Recordings
- Per-speaker audio tracks from Discord voice channels, recorded as raw PCM (48kHz, 16-bit, mono)
- Recording only begins after every participant in the voice channel explicitly consents via the in-channel prompt. If anyone declines, no audio is captured.
- The bot plays a voice announcement when recording begins and ends

### Session Metadata
- Game system (e.g., "D&D 5e") — provided optionally by the session initiator
- Campaign name — provided optionally by the session initiator
- Session number — provided optionally by the session initiator
- Session start/end timestamps
- Number of participants
- Audio quality metrics

### Consent Records
- A record of each user's consent decision (accept or decline)
- Timestamp of consent
- License restriction flags chosen by each participant (see "Licensing Model")

### GM Session Notes
- Text notes submitted voluntarily by the game master after a session
- GMs are reminded not to include personal information about players

### What We Do NOT Collect
- Message content from text channels
- User profile information beyond what is needed for consent tracking
- Server configuration or channel lists
- Direct messages

## Licensing Model

Instead of a single license, participants control how their audio may be used through two independent flags:

- **no_llm_training** — If set, your audio may not be used for training large language models or similar AI systems
- **no_public_release** — If set, your audio is kept in private storage and not included in the public dataset

By default, both flags are off, meaning your audio is released under CC BY-SA 4.0 with no additional restrictions. You can toggle these flags at any time before publication through the participant portal or the Bot's restriction buttons.

## How We Identify You

### In Our Private Storage
- Your Discord user ID and display name are stored in a private file (`pii.json`) used only for internal session management
- This file is **never** included in the public dataset

### In the Public Dataset
- Your Discord user ID is pseudonymized using a SHA-256 hash, truncated to 16 hex characters
- Your display name is not included
- Your audio track filename uses the pseudonymized identifier
- The pseudonymization is one-way — there is no practical way to reverse it to recover your Discord identity

## Where Data Is Stored

- **During recording:** Audio is buffered to the bot's local disk
- **After recording:** Session bundles are uploaded to Hetzner Object Storage (S3-compatible, encrypted at rest)
- **Public dataset:** Validated sessions (where participants have not set `no_public_release`) are published on HuggingFace

## How Data Is Used

Your contributed audio will be:
1. Transcribed using automatic speech recognition
2. Made available for review and correction through the participant portal
3. Reviewed for personal information (automated and manual)
4. Included in a public dataset for training and evaluating transcription models (unless you set `no_public_release`)
5. Licensed according to your chosen restriction flags

## Participant Portal

Every participant can sign in to the participant portal with their Discord account to:

- **Review transcripts** — Read through session transcripts with per-line audio playback
- **Correct transcriptions** — Fix speech recognition errors (corrections also serve as training data)
- **Flag private info** — Mark lines containing personal information for exclusion from the dataset
- **Change license restrictions** — Toggle `no_llm_training` or `no_public_release` per session at any time
- **Download your data** — Export all your sessions, transcripts, and audio files
- **Withdraw consent** — Revoke consent for any session

## Your Rights

### Before Dataset Publication
- You may withdraw consent for any session through the participant portal or by emailing data@sessionhelper.com
- If your audio has not yet been included in a published dataset release, it will be permanently deleted from storage upon withdrawal

### After Dataset Publication
- Published dataset releases under CC BY-SA 4.0 cannot be recalled, as the license grants irrevocable rights to recipients
- However, your audio will be removed from all future dataset releases upon request
- We will make reasonable efforts to notify known redistributors, but cannot guarantee deletion from third-party copies

### GDPR (EU Users)
- **Lawful basis:** Explicit consent (Article 6(1)(a) and Article 9(2)(a) for voice data as biometric data)
- **Right to access:** You may request a copy of all data we hold about you, or download it directly from the participant portal
- **Right to rectification:** You may correct your transcripts through the participant portal
- **Right to erasure:** You may request deletion (subject to the limitations above regarding published releases)
- **Right to data portability:** You may export your data from the participant portal
- **Right to withdraw consent:** You may withdraw consent at any time through the portal or by email
- **Right to lodge a complaint:** You have the right to lodge a complaint with your local data protection authority
- **Data controller contact:** data@sessionhelper.com

## Data Retention

- Raw audio files are retained in private storage until included in a dataset release or deleted upon consent withdrawal
- Sessions not included in a release are deleted within 90 days
- Consent records are retained indefinitely as legal documentation
- Pseudonymized data in published datasets is retained indefinitely under the applicable license

## Age Requirement

You must be at least 18 years old to consent to recording. If you are under 18, you must have parental or guardian consent.

## Third-Party Services

- **Discord:** Audio is captured via Discord's voice API. Discord's own privacy policy applies to your use of Discord.
- **Hetzner Object Storage:** Session data is stored using Hetzner's S3-compatible storage service (EU-based).
- **HuggingFace:** The public dataset is hosted on HuggingFace's platform.

## Changes to This Policy

We may update this privacy policy. Changes will be reflected in the "Last updated" date above. If we make material changes to how we handle your data, we will notify active participants through the Bot or the participant portal. Continued use of the Bot after changes constitutes acceptance.

## Contact

- **Data requests (GDPR, deletion, access):** [data@sessionhelper.com](mailto:data@sessionhelper.com)
- **General inquiries:** [admin@sessionhelper.com](mailto:admin@sessionhelper.com)
- **GitHub:** [sessionhelper/ttrpg-collector](https://github.com/sessionhelper/ttrpg-collector)

---
license: cc-by-sa-4.0
task_categories:
  - automatic-speech-recognition
  - speaker-diarization
language:
  - en
tags:
  - ttrpg
  - tabletop-rpg
  - multi-speaker
  - conversational
  - role-playing
  - discord
  - consent-first
pretty_name: Open Voice Project — TTRPG Session Dataset
size_categories:
  - n<1K
---

# Open Voice Project — TTRPG Session Dataset

A consent-first, community-contributed dataset of tabletop role-playing game (TTRPG) voice sessions recorded from Discord, with per-speaker audio tracks, participant-corrected transcripts, and optional GM session notes.

## Dataset Description

### Summary

This dataset contains multi-track audio recordings of TTRPG sessions (D&D, Pathfinder, Call of Cthulhu, and other systems) contributed by game masters and players through the Session Helper Discord bot. Each session includes:

- **Per-speaker raw PCM files** (48kHz, 16-bit, mono) — one track per consenting participant
- **Participant-corrected transcripts** — ASR output reviewed and corrected by the speakers themselves
- **Session metadata** (game system, duration, participant count)
- **GM session notes** (optional, contributed by the game master)

All data was collected with explicit, informed consent from each participant.

### Two License Tiers

The dataset is split into two subsets based on participant-chosen restrictions:

| Subset | License | Description |
|--------|---------|-------------|
| **ovp-open** | CC BY-SA 4.0 | No additional restrictions. May be used for any purpose including LLM training. |
| **ovp-rail** | CC BY-SA 4.0 + RAIL | Participants set `no_llm_training`. Audio may not be used for training large language models or similar AI systems. All other CC BY-SA 4.0 uses permitted. |

Sessions where any participant set `no_public_release` are not included in this dataset.

A session's tier is determined by its most restrictive participant. If any speaker in a session set `no_llm_training`, the entire session is in the `ovp-rail` subset.

### What Makes This Dataset Unique

- **Consent-first collection**: Every participant explicitly agreed to recording and chose their own license restrictions before any audio was captured
- **Per-speaker tracks**: Clean speaker separation without diarization — each speaker is a separate audio file
- **Participant-corrected transcripts**: Speakers review and correct their own ASR transcripts, producing high-quality ground truth for ASR training
- **Multi-system coverage**: Sessions from multiple TTRPG systems, not just D&D
- **Role-playing speech**: Participants frequently alter their voices for character dialogue, creating a uniquely challenging diarization and ASR benchmark
- **Conversational + narrative**: Mix of out-of-character discussion, in-character dialogue, and GM narration

### Languages

English (primary). Other languages may appear as contributions grow.

## Dataset Structure

```
ovp-open/
  session_{id}/
    meta.json               — session metadata
    consent.json            — pseudonymized consent records with license flags
    audio/
      {pseudo_id}.pcm       — per-speaker raw PCM audio (48kHz, 16-bit, mono)
    transcript.json         — participant-corrected transcript with speaker labels
    notes.md                — GM session notes (optional)

ovp-rail/
  session_{id}/
    (same structure)
```

### Fields in `meta.json`

| Field | Type | Description |
|-------|------|-------------|
| session_id | string | Unique session identifier |
| started_at | string | ISO 8601 timestamp |
| ended_at | string | ISO 8601 timestamp |
| duration_seconds | float | Session duration |
| game_system | string | TTRPG system (e.g., "D&D 5e") |
| campaign_name | string | Campaign name (optional) |
| participant_count | int | Total participants |
| consented_audio_count | int | Participants who consented to audio |
| audio_format | object | `{"encoding": "pcm_s16le", "sample_rate": 48000, "channels": 1}` |
| license_tier | string | `"ovp-open"` or `"ovp-rail"` |
| quality_flags | object | Automated quality checks |

### Pseudonymization

Speaker identifiers are derived from Discord user IDs using SHA-256, truncated to 16 hex characters. The mapping is one-way and cannot be reversed. No Discord usernames, display names, or user IDs appear in the public dataset.

## Collection Process

1. A game master invites the Session Helper Bot to their Discord server
2. Before a session, the GM runs `/record` in a voice channel
3. The bot plays a voice announcement and posts a consent embed — each player must explicitly accept or decline
4. After accepting, each player can toggle `no_llm_training` and/or `no_public_release` restriction flags
5. Recording starts only after all participants have responded
6. Audio is captured as separate per-speaker raw PCM streams via Discord's voice API
7. On `/stop`, audio is pseudonymized and uploaded to Hetzner Object Storage
8. Participants can review and correct transcripts through the participant portal
9. A curation pipeline validates quality and checks for PII
10. Approved sessions are split into `ovp-open` or `ovp-rail` and added to this dataset

### Consent

Every participant received the following information before consenting:
- Audio will be recorded as a separate per-speaker track
- Audio will be transcribed and may be reviewed by participants
- Audio and transcript may be released under CC BY-SA 4.0, subject to chosen restrictions
- Discord identity will be pseudonymized (SHA-256, 16 hex chars)
- Two optional restriction flags available: `no_llm_training`, `no_public_release`
- Consent is withdrawable at any time through the participant portal
- Declining does not require leaving the voice channel

### Personal Information

- Discord user IDs are pseudonymized using SHA-256, truncated to 16 hex characters
- Display names are not included in the public dataset
- GM session notes are reviewed for PII before inclusion
- Participants can flag private information in transcripts through the portal
- Participants who declined recording are not represented in the data

## Intended Uses

- Training and evaluating automatic speech recognition (ASR) models on conversational, multi-speaker audio
- Speaker diarization research, especially for speakers who alter their voices (character voices)
- Natural language processing on TTRPG dialogue and narrative
- Studying conversational dynamics in collaborative storytelling
- Fine-tuning speech models on participant-corrected transcript pairs

**Note:** The `ovp-rail` subset may not be used for LLM/AI model training. Check the `license_tier` field in `meta.json` before use.

## Limitations

- English-dominant (contributions in other languages welcome)
- Audio quality varies by participant's microphone and Discord connection
- Sessions may contain background noise, cross-talk, and ambient sound
- Character voice acting may cause speaker confusion in diarization systems
- GM notes quality and detail vary by contributor
- Raw PCM files are larger than compressed formats; convert to FLAC/WAV as needed for your pipeline

## Citation

```bibtex
@dataset{open_voice_project,
  title={Open Voice Project — TTRPG Session Dataset},
  author={Session Helper LLC},
  year={2026},
  license={CC BY-SA 4.0},
  url={https://huggingface.co/datasets/sessionhelper/open-voice-project}
}
```

## License

- **ovp-open subset:** CC BY-SA 4.0
- **ovp-rail subset:** CC BY-SA 4.0 + Responsible AI License (no LLM training)

## Contact

- Data requests: [data@sessionhelper.com](mailto:data@sessionhelper.com)
- General: [admin@sessionhelper.com](mailto:admin@sessionhelper.com)
- Project: [sessionhelper.github.io/open-voice-project](https://sessionhelper.github.io/open-voice-project/)

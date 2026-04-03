# Consent Text — Open Voice Project

This is the text shown to participants when the Bot requests consent to record.

---

## Voice Announcement

When the GM runs `/record`, the Bot joins the voice channel and plays:

> "This session will be recorded for the Open Voice Project."

## Consent Prompt (Text Channel)

The Bot posts the following embed in the text channel:

---

### Recording Consent — Open Voice Project

This session will be recorded for the Open Voice Project, an open dataset of tabletop RPG audio for speech research and transcription.

By clicking **Accept**, you agree to the following:

1. **Your audio will be recorded** as a separate per-speaker track during this Discord voice session.

2. **Your audio will be transcribed** using automatic speech recognition and may be reviewed and corrected by participants.

3. **Your audio and transcript may be released** as part of a public dataset under the **Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)**, subject to any restrictions you set.

4. **Your Discord identity will be pseudonymized.** Your username and user ID will not appear in the published dataset. Audio files are identified by a truncated SHA-256 hash of your Discord user ID.

5. **You may set restrictions after accepting.** Two optional flags let you control how your audio is used:
   - **No LLM Training** — Your audio may not be used for training AI models
   - **No Public Release** — Your audio stays in private storage and is not published

6. **You may withdraw consent at any time** through the participant portal or by emailing data@sessionhelper.com. If your audio has not yet been published, it will be permanently deleted.

7. **You are at least 18 years old**, or have parental/guardian consent to participate.

---

**Accept** | **Decline**

You can decline without leaving the voice channel. Declining does not affect your ability to participate in the game — your audio simply will not be recorded.

---

## After Accepting

After clicking Accept, the Bot shows restriction buttons:

- **No LLM Training** (toggle)
- **No Public Release** (toggle)

Both default to off (fully open). You can change these at any time during the session or later through the participant portal.

## After All Participants Respond

Once everyone has responded, the Bot plays a voice announcement:

> "Recording has begun."

If anyone declines, no audio is captured from any participant.

## Participant Portal

After the session, you can manage your recordings at any time through the participant portal:

- Review and correct transcripts
- Flag lines containing private information
- Change your license restrictions
- Download your audio and transcripts
- Withdraw consent for any session

For more information:
- [Privacy Policy](https://sessionhelper.github.io/privacy-policy.html)
- [Terms of Service](https://sessionhelper.github.io/terms-of-service.html)
- [Open Voice Project](https://sessionhelper.github.io/open-voice-project/)

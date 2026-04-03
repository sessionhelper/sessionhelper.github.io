# Terms of Service — Session Helper

**Last updated:** 2026-04-02

## 1. Purpose

The Session Helper Bot ("the Bot") records tabletop RPG voice sessions in Discord for the Open Voice Project, a community-contributed audio dataset for speech research and transcription. The Bot and the participant portal are operated by Session Helper LLC, a New Mexico limited liability company. By using the Bot, you agree to these terms.

## 2. Eligibility

- You must be at least 18 years old to use the Bot, or have parental/guardian consent.
- You must have authority to invite the Bot to the Discord server where you use it.

## 3. How It Works

- A server member invokes the `/record` command to start a recording session.
- The Bot plays a voice announcement: "This session will be recorded for the Open Voice Project."
- The Bot posts a consent prompt to all members in the voice channel.
- Recording only begins after every participant in the voice channel explicitly responds. If anyone declines, no audio is captured.
- Each speaker is recorded as a separate audio track (raw PCM, 48kHz).
- After accepting, participants can set license restrictions via the Bot's buttons (see "License Restrictions" below).
- When the GM runs `/stop`, audio is pseudonymized and uploaded to secure storage. The Bot announces "Recording complete."

## 4. Consent

- Recording requires explicit consent from each participant via the Bot's consent prompt.
- You may decline to be recorded without leaving the voice channel. Declining does not affect your ability to participate in the game.
- You may withdraw consent at any time through the participant portal or by emailing data@sessionhelper.com.
- If your audio has not yet been included in a published dataset release, withdrawal results in permanent deletion from storage.

## 5. License Restrictions

By consenting to recording, you grant a non-exclusive, worldwide license under CC BY-SA 4.0 for your audio to be transcribed, included in the dataset, and redistributed under the same license terms.

You may apply additional restrictions through two independent flags:

- **no_llm_training** — Your audio may not be used for training large language models or similar AI systems
- **no_public_release** — Your audio is kept in private storage and not released publicly

By default, both flags are off (fully open). You can change these at any time through the Bot's restriction buttons during a session or through the participant portal after a session. Changing restrictions affects future dataset releases only.

## 6. Participant Portal

The participant portal allows you to manage your data after recording:

- Review and correct transcripts
- Flag lines containing private information for exclusion
- Toggle license restrictions per session
- Download all your data
- Withdraw consent for any session

## 7. Content Guidelines

You agree not to use the Bot to record:
- Content that violates Discord's Terms of Service or Community Guidelines
- Harassment, hate speech, or threats of violence
- Content involving minors without parental consent
- Copyrighted actual-play content from published shows (e.g., recordings of Critical Role, Dimension 20, etc.)
- Content created solely to degrade dataset quality

## 8. GM Session Notes

- Session notes submitted via `/notes` are voluntary contributions.
- You must not include real names, addresses, phone numbers, or other personal information about your players in session notes.
- By submitting notes, you grant a CC BY-SA 4.0 license for their inclusion in the dataset.

## 9. Limitation of Liability

- The Bot and participant portal are provided "as is" without warranties of any kind, express or implied.
- Session Helper LLC is not responsible for content recorded through the Bot. Responsibility for the content of recordings rests with the participants.
- Session Helper LLC's total liability to you for any claims arising from your use of the Bot or participant portal is limited to the amount you have paid to Session Helper LLC (which is zero for free users).
- Session Helper LLC is not liable for any indirect, incidental, consequential, or punitive damages.
- Users who initiate recordings are responsible for ensuring all participants have consented. Session Helper LLC will process DMCA takedown requests; liability for unauthorized recordings rests with the user who initiated the recording.
- Session Helper LLC does not guarantee that data will be deleted from all third-party copies after publication. Once audio is included in a published dataset release under CC BY-SA 4.0, recipients have irrevocable rights under that license.

## 10. Data Handling

See our [Privacy Policy](/privacy-policy.html) for details on data collection, storage, pseudonymization, and your rights.

## 11. Termination

- Session Helper LLC may remove the Bot from any server or ban users who violate these terms.
- You may remove the Bot from your server at any time.
- Termination does not affect license grants already made for published data.

## 12. Governing Law

These terms are governed by the laws of the State of New Mexico, United States.

## 13. Changes

We may update these terms. Changes will be reflected in the "Last updated" date. If we make material changes, we will notify active users through the Bot or participant portal. Continued use after changes constitutes acceptance.

## 14. Contact

- **General inquiries:** [admin@sessionhelper.com](mailto:admin@sessionhelper.com)
- **Data requests:** [data@sessionhelper.com](mailto:data@sessionhelper.com)
- **GitHub:** [sessionhelper/ttrpg-collector](https://github.com/sessionhelper/ttrpg-collector)

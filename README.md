# Daily Dashboard

A finite daily plan for health, mind, schedule, and life. Each day's plan is generated once and frozen; interactions are stored separately and inform history without rewriting the day's prescription.

## V3

- Mobile-first single-page app on GitHub Pages
- Immutable daily card with separate mutable completion/input state
- Mon/Wed/Fri strength prescription and recovery-day movement
- Workout logging, gratitude, nutrition, steps, sleep, and life-maintenance commitments
- Connected health, Google Calendar, and Gmail context
- Encrypted connected-data snapshot using PBKDF2-SHA256 + AES-GCM
- Browser-only sync key stored locally on the user's device
- Scheduled connector refresh handled outside the public site
- JSON export/import for local dashboard history

## Privacy architecture

GitHub Pages and this repository are public, so private connector data is **never stored here as plaintext**. The repository contains only an AES-GCM encrypted payload at `data/connected.enc.json`. The decryption key is not committed to GitHub; it stays in the user's browser and in the private sync workflow.

Private API credentials and OAuth tokens must never be committed to this repository or shipped in client-side JavaScript.

## Daily lifecycle

The private sync process collects the latest connected metrics and publishes a new encrypted snapshot. When the dashboard first opens for a date, it decrypts that snapshot locally and deals that day's card. The plan is then frozen in local storage for that date; checkmarks, gratitude text, and workout results remain editable.

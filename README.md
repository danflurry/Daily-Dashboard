# Daily Dashboard

A finite daily plan for health, mind, schedule, and life. Each day's plan is generated once and frozen; interactions are stored separately and inform the evolving history without rewriting the day's prescription.

## V1

- Mobile-first single-page app
- Mon/Wed/Fri strength prescription with current working weights
- Recovery-day movement prescription
- Nutrition, steps, sleep, gratitude, and life-maintenance commitments
- Workout result logging
- Local persistence and daily history
- JSON export/import
- Integration placeholders for Fitbit and Calendar

## Architecture

V1 is intentionally static and safe for GitHub Pages. Private API credentials must never be placed in this repository or client-side JavaScript. Live Fitbit, Calendar, Gmail, and other private integrations should be connected through a small authenticated backend in a later version.

## GitHub Pages

The site is plain HTML/CSS/JavaScript with no build step. Configure GitHub Pages to deploy from the `main` branch at `/ (root)`.

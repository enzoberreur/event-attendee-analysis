# Event Attendee Analysis

A browser-based recruiting intelligence tool. Upload a LinkedIn recruiter CSV extract and get instant analysis of your event attendees — seniority breakdown, geographic reach, industry mix, actionable shortlists, and an AI assistant.

## Live Demo

**[Open the tool](https://YOUR_USERNAME.github.io/event-attendee-analysis/)**

## What It Does

- **Dashboard** — 6 analytical dimensions: seniority, geography, industry, top companies, skills, and university pedigree
- **Actionable Insights** — Prioritized cards: competitor talent to poach, high-fit candidates, scarce Data/AI profiles, coverage gaps
- **Methodology** — Full transparency on every metric: how it's calculated and what the limitations are
- **AI Assistant** — Chat with your data. Shortlist candidates, generate outreach messages, compare events

## How to Deploy

1. Fork this repository
2. Go to **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Choose `main` branch, `/ (root)` folder
5. Click **Save**
6. Your tool will be live at `https://YOUR_USERNAME.github.io/event-attendee-analysis/`

That's it. No build step, no dependencies, no server.

## How It Works

Everything runs in the browser. The CSV is parsed client-side, classifications are computed in JavaScript, and the AI assistant calls Claude's API directly from the browser (no API key needed when accessed through Claude artifacts).

### Classification Approach

| Metric | Method |
|--------|--------|
| Seniority | Multi-signal cascade: company type → title keywords (6 languages) → headline → pipeline hints |
| Geography | 150+ city/country keywords mapped to 6 world regions |
| Industry | Company-first (100+ firms mapped), title fallback only |
| Universities | Scans headline + company + title for 25+ university patterns |
| Skills | Keyword matching across 8 domains on headline + title |

## Privacy

All data processing happens in your browser. No data is sent to any server except when using the AI assistant (which sends a summary to Claude's API for analysis). No data is stored.

## Expected CSV Format

Standard LinkedIn recruiter export with columns:

```
First Name, Last Name, Headline, Location,
Current Title, Current Company, Email Address,
Phone Number, Profile URL, Active Project,
Notes, Feedback
```

## License

MIT

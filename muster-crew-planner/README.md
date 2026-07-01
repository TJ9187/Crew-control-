# Muster — Crew Operations Platform (M/Y Renaissance)

A single-file web application for planning superyacht crew rotations and managing the
travel, documents and logistics that go with them. Built to replace the fragile leave
and crew-movement spreadsheets with a live, role-aware planner.

> **This repository ships with scrubbed sample data.** All crew names, passport numbers,
> dates of birth and places of birth are fabricated. No real personal data is included.
> See [Data](#data) below before connecting real records.

## Quick start

No build step and no dependencies — the app is one self-contained HTML file.

1. Open `index.html` in any modern browser (Chrome, Edge, Safari, Firefox), **or**
2. Serve it (e.g. GitHub Pages) and visit the URL.

On the sign-in screen choose a role:

- **Purser** — full access; maintains travel documents and blackout dates.
- **Captain** — full fleet visibility; maintains the day-to-day itinerary (with the Purser).
- **HOD** (Bosun / Chief Engineer / Interior Manager / Head Chef) — see the whole fleet, edit their own department.
- **Crew member** — a personal, phone-style app (pick a name to preview).

## Features

- **Live Dashboard** — comings & goings with today / week / month counts, a period-linked
  itinerary ribbon, and a movements feed colour-coded by department. Travel documents flip
  from red to green as crew acknowledge them.
- **Crew Movements** — flights, ground transfers and hotels in one tab, with nationality,
  immigration-required and travel-document status.
- **Rotation Calendar** — Annual / Monthly / Weekly zoom, filter by department or rank,
  itinerary and blackout windows overlaid, click to add or edit leave.
- **Crew Status** — live status plus passport details, with a one-click **official
  flag-state crew list** you can view, print, save as PDF, email or export to CSV.
- **Itinerary & Blackouts** — day-to-day port calls and confirmed / potential charters
  (Bridge & Purser), plus blackout windows where no swap-outs are allowed (Purser).
- **Crew App** — each crew member sees their trips, acknowledges documents, views leave &
  itinerary, requests leave, and submits Off-Route Travel (ORT) requests that route to
  their HOD and then the Captain.

## Data

The app reads four in-file datasets (embedded near the top of the `<script>` block):

| Constant | Contents |
|----------|----------|
| `DATA`   | Crew roster: name, rank, department, entitlement, leave events |
| `MOVES`  | Crew movements: flights, dates, immigration / travel-doc flags |
| `LOGI`   | Ground transfers and hotel bookings |
| `CLIST`  | Crew-list passport data + vessel particulars |

All values in this repo are **sample data**. To run against real records, replace those
constants with your own data in the same shape. **Do not commit real crew personal data
to a public repository** — passport numbers, dates of birth and places of birth are
personal data subject to GDPR. Keep production data in a private, access-controlled store.

## Roadmap

Hosted multi-user version with real authentication and a shared database, live flight-status
integration, push notifications, per-document acknowledgement, and write-back of approved
leave into the calendar.

## Notes

- Edits made in the app (leave, itinerary, acknowledgements, requests) are in-session only
  in this prototype; they reset on reload. Persistence arrives with the hosted build.
- Country flags load from a CDN when online and fall back to a country-code chip offline.

---
Prototype — M/Y Renaissance. Sample data only.

# Kyrgyzstan Itinerary — Codex Project Instructions

## Project purpose

- Maintain a lightweight, public GitHub Pages site for the 2026 Kyrgyzstan 8-day private horse-riding and hiking itinerary.
- Preserve a fast, readable experience on desktop and mobile.
- Keep the current D1–D8 card interaction and the synchronized Leaflet map working.

## Current repository structure

- `index.html`: Production website, including HTML, CSS, itinerary data, Leaflet map setup, and JavaScript interactions.
- `README.md`: Human-facing repository description.
- `AGENTS.md`: Persistent instructions for Codex.

Keep the single-file structure unless splitting files materially improves maintainability. Ask before introducing a framework, build system, package manager, or multiple production files.

## Required behavior

- Support desktop and mobile layouts down to 320 px wide.
- Preserve all eight D1–D8 controls.
- Selecting a day must update both the daily detail section and the map.
- The map must show every listed stop for the selected day, connect stops in itinerary order, and fit the view to that day's locations.
- D1 must show Bishkek and Ala Archa once each and identify the journey as a return trip.
- Keep keyboard-accessible native buttons and visible focus states.
- Keep OpenStreetMap attribution visible.
- Prefer Traditional Chinese for user-facing explanations; established English place names may remain in English.

## Map and dependency rules

- Use Leaflet with OpenStreetMap unless the user explicitly approves a change.
- Do not introduce services that require an API key, account, payment method, or usage billing without explicit approval.
- Pin external library versions rather than using an unversioned latest release.
- Treat itinerary coordinates as reference points, not navigation-grade tracks.
- Do not invent or silently guess a location, route, travel time, accommodation, meal, or activity detail.
- If a place is ambiguous, verify it with reliable sources or label it clearly as approximate and ask for tour-operator GPS data.
- Straight lines on the map are itinerary-order illustrations, not road, hiking, or horse-riding navigation routes.

## Content and privacy rules

- This repository and its GitHub Pages site are public.
- Never add passport data, visa identifiers, booking references, insurance numbers, payment records, private phone numbers, live room numbers, credentials, tokens, or other sensitive personal information.
- Do not publish precise real-time personal location information.
- Preserve the supplied dates, durations, prices, inclusions, exclusions, and accommodation wording unless the user supplies an update.
- Do not translate or rename a place in a way that could change which geographic location it identifies.

## Change workflow

1. Read the current `index.html` and this file before proposing changes.
2. For ambiguous visual or behavioral requests, ask focused questions before editing.
3. Make the smallest coherent change that satisfies the request.
4. Preserve unrelated layout, content, and functionality.
5. Avoid destructive rewrites when a targeted edit is sufficient.
6. Explain any external dependency, privacy implication, or uncertain geographic assumption.
7. Show the resulting diff and summarize user-visible changes.

## Validation requirements

After modifying the site:

- Validate that the HTML document still contains one usable page entry point.
- Check JavaScript syntax and confirm that the browser console has no new errors.
- Load the page through a local HTTP server rather than relying only on a `file://` preview.
- Click D1 through D8 and confirm each selection updates:
  - selected-card state;
  - day title and date;
  - route text;
  - activity, transport, and accommodation details;
  - map title and note;
  - map markers and connecting line;
  - automatic map bounds.
- Verify at a desktop width around 1280 px and a mobile width around 390 px.
- Confirm that no text, controls, map attribution, or popup content is clipped or overlapping.
- Confirm external Leaflet assets and OpenStreetMap tiles load successfully.
- If full browser testing is unavailable, state exactly which checks were completed and which remain for the user.

## Git and delivery rules

- Do not commit directly to `main` unless the user explicitly requests it.
- Prefer a focused branch and pull request for functional or layout changes.
- Use short, descriptive commit messages such as `Add daily map markers` or `Improve mobile card layout`.
- Do not commit generated screenshots, temporary files, logs, secrets, or editor-specific files.
- Before delivery, review the diff for accidental changes and disclose any known limitation.
- GitHub Pages deploys from the configured publishing source; do not change that source without explicit approval.

## Definition of done

A task is complete only when the requested behavior is implemented, relevant checks pass, the existing itinerary remains intact, mobile behavior is considered, privacy rules are respected, and the final response identifies any unverified item.

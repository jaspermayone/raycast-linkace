# LinkAce Raycast Extension

Add links to your LinkAce instance from Raycast, modeled after your Apple Shortcut flow:
- Accept URL from form or clipboard
- POST to `/api/v2/links` with your API token
- Parse `id` in response
- Show success/failure toasts

## Setup

1) In Raycast Preferences → Extensions → Developer Tools: enabled
2) Clone this folder or create files as shown
3) Install deps:
   - `npm i`
4) Configure preferences in Raycast:
   - LinkAce Base URL (e.g., https://linkace.example.com)
   - API Token (password type)
   - Optional default tags
   - Private by default (checkbox)
5) Run:
   - `npx raycast dev`
6) Build:
   - `npx raycast build`

## Security
- API token stored in Raycast preferences (password type). Do not hardcode or commit it.
- We never log the token; headers are set at request time.

## Notes
- If server returns non-2xx, we surface body text (when available) in the toast, similar to the Shortcut’s “Something went wrong…” alert.
- URL validation is light; server-side validation still applies.

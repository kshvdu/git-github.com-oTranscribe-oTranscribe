---
name: otranscribe
description: Use when the user wants to transcribe recorded interviews, audio or video with oTranscribe (free web app), run or build it locally, or read/write its .otr files. Triggers on "oTranscribe", "transcribe interview", ".otr file".
---

# oTranscribe

Free web app (oTranscribe/oTranscribe on GitHub) for manually transcribing audio, video and YouTube. It does not auto-transcribe; the user types while the player is controlled by keyboard.

## Using the app
- Web version: otranscribe.com. Works with audio/video files and YouTube links.
- Keyboard: ESC pause/play, F1 rewind, F2 fast-forward, F3/F4 slower/faster. Speed slider also available.
- Transcript autosaves to browser `localStorage` every second. Clearing site data loses it, so export regularly.
- Text is rich (contentEditable).

## Self-hosting
Requires Node v24+ and npm v10+.
1. `npm install`
2. `npm run build` -> outputs `dist/`; upload `dist/` to any server.
3. `npm run serve` serves the production build (Workbox offline caching).
4. `npm run dev` starts the dev server at http://localhost:8080/ (no offline caching).

Chrome may block local file:// copies; serve over http.

## .otr file format
JSON with keys:
- `text`: raw HTML of the transcript
- `media`: last media name (optional)
- `media-source`: link to last media (optional)
- `media-time`: last playtime (optional)

To convert to plain text, parse the JSON and strip HTML tags from `text`.

## Limits
Facts here come from the repo README. Check the repo before claiming other features or version-specific behaviour.

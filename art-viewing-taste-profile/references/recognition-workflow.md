# Artwork Recognition Workflow

Goal: let users avoid photographing wall labels, while still making AI recognition auditable and correctable.

## Steps

1. Produce a neutral visual description: medium clues, subject matter, composition, colors, text visible in the image, installation context, and any signature or label fragments.
2. Generate artwork candidates. Use visual clues, OCR clues, known exhibition context if provided, and host/runtime web search only when available.
3. Attach evidence for each candidate: visual match, text clue, exhibition context, source URL if real, and confidence.
4. Select one candidate only when evidence is adequate.
5. Fallback to `unidentified` when evidence is weak; describe the image and ask the user to optionally fill title/artist.

## Recognition Status

- `probable`: one candidate is plausible, but not user-confirmed.
- `confirmed`: user or reliable label/source confirms identity.
- `unidentified`: no reliable identity; use visual description only.
- `user_edited`: user has overridden AI identity.

## Candidate JSON

```json
{
  "title": "Artwork title or null",
  "artist": "Artist name or null",
  "year": "Year or date range or null",
  "medium": "Medium or null",
  "source_url": "Verifiable source URL or null",
  "confidence": 0.0,
  "evidence": [
    "Visible visual clue",
    "OCR or signature clue",
    "Search/source clue"
  ]
}
```

## Anti-Hallucination Rules

- Do not fill title, artist, year, or source URL only because the work resembles a known artwork.
- Use low confidence when only style similarity exists.
- For installation, performance, video, and partial-detail photos, prefer `unidentified` unless there is clear source evidence.
- Keep candidates even when uncertain; they are useful as search leads, not final truth.

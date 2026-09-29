# Content review — gaps found in the source rule book

Found while reconciling the site against `2026 OTTPA Rule Book - Working.docx`
(Technical Services/Rules, Drive file `1Sc35jykQka__RXkzpUIhNVzRNLaRLQb5`,
last modified 2026-06-25). Confirmed present in a completely independent, fresh
pandoc conversion of the current docx — not a tooling artifact from the earlier
proof-of-concept. Not fixed here; nothing below was guessed at.

## Isolated single-rule gaps (20)

A rule number exists in the sequence but its text is empty. In each case the
numbering before and after is otherwise normal (e.g. rule 3, then a blank
rule 4, then rule 5 continues) — this reads like a rule whose text was
deleted but the numbered line stayed behind, or a rule number reserved for
something removed. Only you can tell which.

| File | Section | Missing item | Between |
|---|---|---|---|
| 17-section-10 | 10.17 - Supercharger | 4. | "High Helix is maximum 6.5 degrees..." → "The maximum outside diameter..." |
| 18-section-11 | 11.1 - Competitor Safety | 2. | "...full 360-degree neck collar..." → "Fire Retardant Gloves are required" |
| 18-section-11 | 11.10 - Supercharger Safety | 5. | "...mounted to the intake manifold..." → "All centrifugal superchargers must use..." |
| 18-section-11 | 11.11 - Turbocharger Safety | 8. | "...exhaust stacks need to remain intact..." → "Turbo Exhaust Wheel Containment –" |
| 18-section-11 | 11.15 - Clutch / Transmission | 3. | "Clutch must be SFI 1.1 or SFI 1.2 approved." → "All V8 engines must utilize a 'block saver'..." |
| 19-section-12 | 12.4 - High Pressure Common Rail Fuel System | 1. | (whole rule 1 is empty — section has no content) |
| 19-section-12 | 12.5 - Engine | 6. | "No electronic fuel injectors..." → end of section |
| 20-section-13 | 13.4 - Engine | 9. | "No traction control, no digital boxes." → end of section |
| 21-section-14 (LPD30) | 14.1 - General Rules | 4. | "Exhaust manifold and exhaust turbo blankets..." → "No traction control permitted." |
| 21-section-14 (LPD30) | 14.3 - Body / Chassis | 5. | "Must have tonneau cover and tailgate..." → end of section |
| 22-section-15 (PSD26) | 15.3 - Body / Chassis | 11. | "Batteries cannot be located within the cab..." → end of section |
| 24-section-17 (4WD) | 17.2 - Drawbars/Hitch | 11. and 12. | "No drawbar angle greater than..." → [11 blank] → [12 blank] → "Maximum hitch height shall be 26 inches..." |
| 26-section-19 (NA2WD) | 19.3 - Engine | 7. | "Billet engine blocks are not allowed." → "Aluminum heads allowed." |
| 28-section-21 | 21.2 - Tractor General: Safety | 1. (sub-item) | "...minimum of 3 restraining cables/straps..." → end of section |
| 30-section-23 (MOD) | 23.4 - Engine Combinations | 20. | (trailing item, end of section) |
| 34-section-27 (LPS) | 27.4 - Turbocharger | 9. and 10. | trailing items, end of section |
| 39-section-32 (LSS) | 32.4 - Engine | 3. | "OEM canted valve heads allowed." → "No V8 engines are allowed in Light Super Stock class." |
| 41-section-34 (LMRT) | (see garbled section below) | 4. | trailing item before Section 34.6 |

## Garbled / structurally scrambled sections (5)

These aren't a single missing sentence — the list numbering itself is
scrambled (e.g. "2. 1." nested inside itself, or a heading that reads
"1.  1." instead of real title text). This is consistent in both the old
and fresh pandoc conversions, so it's not a conversion bug — something in
the Word doc's list/heading structure isn't extracting as plain text at
all (could be a diagram, a table, or SmartArt with real content that a
text extractor can't see). These need to be opened directly in Word to
see what's actually there:

- **18-section-11 → 11.11 - Turbocharger Safety** (items 2–3 garbled)
- **28-section-21 → 21.4 - Tractor General: Roll cage** (items 1–4 heavily garbled)
- **30-section-23 → 23.4 - Engine Combinations** (item 19–20 area garbled)
- **34-section-27 → 27.4 - Turbocharger** (items 5–10 all empty/garbled)
- **41-section-34 → between 34.5 Drawbar/Hitch and 34.6 Front Skid Plate** — an
  entire heading is missing (renders as literal "1.  1.") with several empty
  sub-items. Section 34.6 itself says "configured according to diagram and
  dimensions as follows" — this missing chunk may be (or reference) a
  diagram that didn't survive extraction.

## Also flagged (already fixed, no action needed)

- Two "Refer to rule 20.6.3 'Tractor General: Turbochargers'" cross-references
  (in LLP §25.5 and 540 Light Pro Stock §28.5) quote a title that only exists
  at **21.6**, not 20.6 — Section 20 is Pro Stock Semi Trucks and its 20.6 is
  Engine, not Turbochargers. The number looks stale from a prior renumbering.
  Linked the quoted title to the correct target (21.6) rather than the
  mismatched number; left the visible "20.6.3" text alone rather than
  silently rewrite it. Worth a scan of the live docx for other stale
  cross-reference numbers if you want that done.

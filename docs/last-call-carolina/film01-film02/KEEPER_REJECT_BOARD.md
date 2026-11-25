# Keeper / reject board

Rule: one hard failure rejects the take. Do not salvage with zooms, speed ramps, or still holds.

## KEEP

| ID | File (Mac) | Why it stays |
|---|---|---|
| Film 02 **S01_01** | `Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/clips/S01_01.mp4` | Hollow truck. Native motion. Story-true to “left the holler / truck bed full of doubts.” |

Re-check S01_01 on Mac anyway (fps, continuous motion, no freeze, no Chi unless accurate). If it fails Pour QA, regenerate from the S01 prompt in `film02/DREAMINA_PROMPTS.md` — that is a new take, not a license to change the shot’s job.

## HOLD — not keepers, but keep the files (2026-08-13)

| ID | Why not keep | Rule |
|---|---|---|
| Film 01 **F01-A.mp4** | Fake readable script, smeared hand, disembodied hand | Hold the file. No second A unless Brandon says |
| Film 01 **F01-K** candidate | NOT KEEP per Brandon/CoS | Hold the file. Do not retake. Spend freeze in effect |

## REJECT — do not download again, do not put on the timeline

| ID | Failure | Do not retry |
|---|---|---|
| Film 01 **F01-J.mp4** | Wrong job, portal ending, melt | The J recipe as written; new J strategy needs Brandon |
| Film 02 **S03** all takes | Rearview interior, mannequin driver, Ken Burns on a still ridge | Interior cabin + rearview glass + any still-zoom |
| Film 02 **S13** all takes including medium regen | Melting / mutating banjo hands | Close or medium hero-hands on the fretboard |
| Film 01 wrench / valve / hose match | Reads as maintenance, not Layer 2→3 | Tool-match into Carolina |
| Film 01 Extended 422.1s / unified 594s | Quarantined branches | Those timelines |
| Generic Chi / yellow lab / shepherd | Wrong dog | Any “dog in truck” without Carolina-dog lock |
| Ken Burns / slideshow / still + push-in | Fails Pour bar | Image-to-video from a single still with no independent camera+subject motion |
| Generated Brandon face | Brand + likeness | Face-hero shots |
| Readable UI, logos, fake documents | History/rights gate | Close-ups of screens with invented text |

## QUEUED — not keepers until QC

| Recipe | Job | Status |
|---|---|---|
| **recipe-v2 exterior truck** | Legal S03 replacement: ridge recedes, camera **outside** the moving truck, no faces in glass | Queued in Dreamina. **Download → frame-verify → QC.** |
| **recipe-v2 wider banjo** | Legal S13 replacement: instrument in a wide/medium-wide frame so hands are not anatomy-hero | Queued in Dreamina. **Download → frame-verify → QC.** |

If either queued take fails, use the fallback prompts in `film02/RECIPE_V2.md`. Do not fall back to the rejected recipes.

## Chi / Chye lock

- Name: **Chye / Chi**, pronounced **“chai.”**
- Breed: **Carolina dog** (American dingo): lean primitive, short golden/yellow coat, **pricked pointed ears**, **fishhook tail**, almond eyes. Not a Labrador, not a German Shepherd, not a yellow mix with floppy ears.
- Film 01: **omit**. Notion lock: she does not belong in the prologue without approved real reference stills.
- Film 02: **omit by default.** No Chi shot is required to tell Appalachian Son. If a future take includes her, it must pass breed QC on every extracted frame or the shot is omitted, not “close enough.”

## Promotion rule

A clip becomes KEEP only after:

1. `ffprobe` shows native video (not a 1-frame still stretched).
2. Five extracted frames show **different subject/camera positions**.
3. Pour QA checklist is all PASS.
4. Filename is copied into Mac `STATUS.md` and (on the next repo pass) this board.

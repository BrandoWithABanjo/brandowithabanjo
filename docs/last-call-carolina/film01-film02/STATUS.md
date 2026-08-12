# STATUS — keepers vs still-needed (2026-08-12)

Cloud run: **docs + paste-ready gens only**. Picture files live on the Mac. BrowserClaw/Dreamina: **offline from this VM**.

## Film 02 — picture

| Shot | Intent | Status | Next |
|---|---|---|---|
| **S01** | Hollow truck leaving the holler | **KEEP** `clips/S01_01.mp4` | Frame-verify once on Mac; do not regen unless it fails Pour QA |
| **S02** | Truck-bed / gravel departure, native motion | **NEEDED** | Generate from film02 prompts |
| **S03** | Ridge fading / “rearview” beat | **REJECTED** (all interior rearview, mannequin, Ken Burns) | Replace with **recipe-v2 exterior truck** — queued, **not downloaded/QC’d** |
| **S04** | City lights rising (Raleigh/Charlotte approach) | **NEEDED** | Generate |
| **S05** | Suit / borrowed time (hands, wardrobe, city glass — no face hero) | **NEEDED** | Generate |
| **S06** | Night room, fiddle as physical object calling | **NEEDED** | Generate |
| **S07** | Chorus 1 gravel run / mountain blood | **NEEDED** | Generate |
| **S08** | Blue Ridge morning | **NEEDED** | Generate |
| **S09** | Creek bed, skipping stones | **NEEDED** | Generate |
| **S10** | Granddad’s plow — tool + earth, not melting hands | **NEEDED** | Generate |
| **S11** | Modern phone vs home (prop, not UI wall) | **NEEDED** | Generate |
| **S12** | Chorus 2 skyline → cabin sun | **NEEDED** | Generate |
| **S13** | Banjo rolling in the chest | **REJECTED** (all banjo incl. medium regen — melting hands) | Replace with **recipe-v2 wider banjo** — queued, **not downloaded/QC’d** |
| **S14** | Bridge: fiddle through a crowd | **NEEDED** | Generate |
| **S15** | Final chorus Boone → Charlotte travel | **NEEDED** | Generate |
| **S16** | End hold: still carrying where I’m from | **NEEDED** | Must inherit Film 01 last frame language |

Shot IDs S01 / S03 / S13 are **Mac-locked**. S02, S04–S12, S14–S16 are this pack’s lyric-board reconstruction for the remaining 2:52. If Mac `film02-appalachian-son-rebuild/` uses different numbers, **keep S01/S03/S13 meanings** and remap the rest; do not revive rejected recipes.

### Film 02 audio

**LOCKED.** `Appalachian_Son_APPLE_MUSIC_LENGTH_172s.wav` · 172.091s.

### Film 02 CapCut

**Not started** (insufficient keepers). Timeline recipe is in `film02/CAPCUT_ASSEMBLY.md`.

## Film 01 — picture

| Module | Intent | Status | Next |
|---|---|---|---|
| F01-A | Layer 1 ordinary room, question + key | **NEEDED** | Generate (v02 Patch A replacement) |
| F01-B | Nottingham 1812 mill floor | **NEEDED** | Generate |
| F01-C | Railway 1830 | **NEEDED** | Generate |
| F01-D | Photography 1839 | **NEEDED** | Generate |
| F01-E | Radio 1925 | **NEEDED** | Generate |
| F01-F | Television 1948 | **NEEDED** | Generate |
| F01-G | Y2K midnight | **NEEDED** | Generate |
| F01-H | MP3 / dorm / rights conflict | **NEEDED** | Generate |
| F01-I | Generative AI + human review | **NEEDED** | Generate |
| F01-J | Foundry close, 25 shutters, string into aperture | **NEEDED** | No wrench/valve |
| F01-K | Carolina world establish + hold for Film 02 frame 0 | **NEEDED** | Joint seam with Film 02 S16/S01 world |

### Film 01 audio

**LOCKED.** `Film01_Tech_Shifts_3326a21e` · ~180.88s · `TAKE_PICK.md` written. Cue-snap on Mac.

v01 174.8s / 30fps master remains comparison authority only.

## First Mac actions (ordered)

1. Unblock OS permission dialog so BrowserClaw can talk to Dreamina.
2. Download recipe-v2 clips. Save under `film02-appalachian-son-rebuild/clips/recipe-v2/`.
3. Frame-verify + Pour QA. Pass → promote to S03 and S13. Fail → regen from RECIPE_V2 fallbacks (do not reuse rejected interior/close-hand prompts).
4. Confirm S01_01 still passes (motion, not a still; no Chi unless accurate).
5. Queue remaining Film 02 shots S02, S04–S12, S14–S16.
6. Queue Film 01 F01-A…K, snapping in/out to TAKE_PICK.md.
7. CapCut only after each film has a full passable picture spine — **no Ken Burns coverage holes**.

## What this PR did / did not do

**Did:** durable production pack in-repo; Film 01 tech-arc prompts; Film 02 remaining-shot prompts; recipe-v2; reject board; Pour QA; CapCut recipes; Mac worker runbook.

**Did not:** generate or download any mp4; QC any frame; write Mac `STATUS.md`; mux audio; export masters.

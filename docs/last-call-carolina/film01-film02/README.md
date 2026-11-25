# Last Call Carolina — Film 01 + Film 02 production pack

**Cinema destination:** 2 Dollar Pour bar. If a shot would not survive next to `~/Downloads/TwoDollarPour_MV_1080p24.mov` with nobody told it was AI, it does not ship.

This pack is the **shot engine** for:

| Film | Title | Locked audio | Picture target |
|---|---|---|---|
| **01** | Tech Shifts prologue (Suno `3326a21e`) | ~180.88s (~3:00.88) | 1920×1080 · **24fps** · mute all gen audio |
| **02** | Appalachian Son (Apple Music length) | **172.091s (2:52.091)** | 1920×1080 · **24fps** · mux locked WAV |

Public identity on every frame: **@brandowithabanjo**. No legal name on screen. No generated Brandon face. Chi/Chye (Carolina dog, pronounced “chai”) is **omit-or-accurate** — Film 01 omits; Film 02 omits unless a take passes breed QC.

---

## Blunt status (2026-08-12 cloud run)

**This VM cannot generate, download, or QC picture.**

| Need | This cloud run | Mac worker (unblocked) |
|---|---|---|
| Locked WAVs | Paths documented only | Files exist under `Documents/Codex/2026-08-12/` |
| Dreamina / Seedance | **Blocked** — BrowserClaw MCP `error`; no private worker; `127.0.0.1:9210` is Mac-localhost | Generate + download recipe-v2 and remaining shots |
| Frame-verify / QC | Rubric only | Extract frames, pass/fail, regenerate |
| CapCut conform | Timeline recipe only | Import WAV once, assemble keepers, export |
| Pour master reference | Not on this disk | `~/Downloads/TwoDollarPour_MV_1080p24.mov` |

Do **not** treat this PR as finished films. Treat it as the paste-ready board a Mac agent runs the moment OS permission dialogs unfreeze.

**Keeper on disk (Mac only):** `film02-appalachian-son-rebuild/clips/S01_01.mp4` — hollow truck.  
**Hard rejects:** all S03 rearview / mannequin / Ken Burns; all S13 banjo including medium regen (melting hands).  
**Queued, not verified:** recipe-v2 exterior truck + wider banjo — **first Mac action = download, frame-verify, QC**.

---

## Read order

1. [PLAN.md](PLAN.md) — end-to-end boards → Dreamina → QC → CapCut
2. [STATUS.md](STATUS.md) — keepers vs still-needed gens
3. [LOCKED_AUDIO.md](LOCKED_AUDIO.md) — WAV paths, durations, decoys
4. [KEEPER_REJECT_BOARD.md](KEEPER_REJECT_BOARD.md)
5. [QUALITY_BAR.md](QUALITY_BAR.md) — Pour QA rubric
6. [MAC_WORKER_DREAMINA.md](MAC_WORKER_DREAMINA.md) — exact Mac / BrowserClaw steps
7. Film 01: [film01/SHOT_LIST.md](film01/SHOT_LIST.md) · [film01/DREAMINA_PROMPTS.md](film01/DREAMINA_PROMPTS.md) · [film01/CAPCUT_ASSEMBLY.md](film01/CAPCUT_ASSEMBLY.md)
8. Film 02: [film02/SHOT_LIST.md](film02/SHOT_LIST.md) · [film02/RECIPE_V2.md](film02/RECIPE_V2.md) · [film02/DREAMINA_PROMPTS.md](film02/DREAMINA_PROMPTS.md) · [film02/CAPCUT_ASSEMBLY.md](film02/CAPCUT_ASSEMBLY.md)

---

## What this cloud run will not fake

- Video files, Dreamina job IDs, download URLs, “QC passed” stamps, or CapCut exports
- Suno credentials, Dreamina logins, or BrowserClaw session cookies
- Exact TAKE_PICK cue times from the 180.88s WAV (file is Mac-only; Film 01 cuts snap to `TAKE_PICK.md` on the Mac)

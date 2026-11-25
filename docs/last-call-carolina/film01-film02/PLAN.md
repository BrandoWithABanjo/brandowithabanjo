# PLAN — Film 01 + Film 02 to the Pour cinema bar

Harness note: this is the plan. Execution of picture gens is Mac-only. This repo lands the complete shot pack so the Mac worker does not invent boards.

## Goal

Ship two continuous-motion cinema pieces that play as one handoff:

1. **Film 01** — technology-history prologue, locked Suno `Film01_Tech_Shifts_3326a21e`, ~180.88s.
2. **Film 02** — Appalachian Son, locked Apple-length WAV 172.091s, opening from Film 01’s last approved frame.

Quality test: would this shot survive if nobody knew AI was involved, sitting next to `TwoDollarPour_MV_1080p24.mov`?

## Non-negotiables

- Photoreal **native motion only**. One camera move per generation. No Ken Burns, stills, slideshows, optical-flow morphs, portals, particles, liquid dissolves.
- Anatomy holds for the whole clip. Melting hands, extra fingers, mannequin skin, wax faces = reject, do not “fix in CapCut.”
- Chi/Chye: Carolina dog (American dingo, golden coat, pricked ears, fishhook tail) **accurate or omit**. Film 01: omit. Film 02: omit by default.
- No generated Brandon face. Hands / back / silhouette / instrument only. On-screen brand is `@brandowithabanjo`.
- Generator audio is **muted**. Only the locked WAVs play.
- Picture conform: **1920×1080 · 24fps CFR** to match Pour. Old Film 01 v01 at 30fps is reference-only, not the new export spec.

## Pipeline (both films)

```
LOCKED WAV
    → lyric / chapter board (this pack)
    → paste-ready Dreamina Seedance prompts (this pack)
    → Mac BrowserClaw generates + downloads
    → frame-verify (0 / 25 / 50 / 75 / 100%)
    → Pour QA rubric pass/fail
    → one silent atomic picture carrier
    → CapCut: WAV once + picture once
    → export 1080p24, mux locked audio bit-identical
```

Cheap blocking on Seedance 2.0 Mini is allowed **only** to prove camera path. Hero takes: Seedance 2.0 1080p/4K, or 2.5 only for the Film 01→02 aperture handoff if 2.0 cannot hold a continuous threshold.

## Phase A — Mac unblock (blocker, not optional)

BrowserClaw on Brandon’s Mac: `http://127.0.0.1:9210/mcp`. Currently frozen behind an OS permission dialog from Grok Bot. This cloud VM cannot reach it.

When unblocked, follow [MAC_WORKER_DREAMINA.md](MAC_WORKER_DREAMINA.md). Do not invent credentials.

## Phase B — Film 02 picture (start here: one keeper already exists)

1. **Download + QC recipe-v2** (already queued in Dreamina): exterior truck, wider banjo. See [film02/RECIPE_V2.md](film02/RECIPE_V2.md).
2. If recipe-v2 fails Pour QA, regenerate with the fallback prompts in that file (wider still; no glass faces; no hero hands).
3. Keep `clips/S01_01.mp4` (hollow truck). Do not regenerate S01 unless QC on the keeper itself fails.
4. Generate remaining native-motion shots **S02, S04–S12, S14–S16** from [film02/DREAMINA_PROMPTS.md](film02/DREAMINA_PROMPTS.md). Never retry rejected S03 interior rearview or S13 close/medium banjo recipes.
5. Assemble per [film02/CAPCUT_ASSEMBLY.md](film02/CAPCUT_ASSEMBLY.md) against 172.091s WAV.

## Phase C — Film 01 picture (parallel once Dreamina is free)

1. Confirm `TAKE_PICK.md` + primary WAV `Film01_Tech_Shifts_3326a21e` (~180.88s). Snap module in/out to that cue map; the times in [film01/SHOT_LIST.md](film01/SHOT_LIST.md) are proportional until the Mac measures the WAV.
2. Generate F01-A through F01-K from [film01/DREAMINA_PROMPTS.md](film01/DREAMINA_PROMPTS.md).
3. Layer 2→3 transition is **string-and-aperture only**. Wrench / valve / hose match is still rejected (Notion Film 01 v02 lock).
4. Last 0.4s of Film 01 must be a still-hold of the approved Carolina frame that Film 02 frame 0 inherits. First committed boot/step lives in Film 02, not Film 01.
5. Assemble per [film01/CAPCUT_ASSEMBLY.md](film01/CAPCUT_ASSEMBLY.md).

## Phase D — Joint seam

Film 01 last frame = Film 02 first frame (same lens, light, terrain, weather, character position). Do not dissolve. Do not regenerate the whole of either film to fix the seam — generate one joint plate if needed.

## Phase E — Export + log

- Film 01 filename: `Film01_Tech_Shifts_v02_1080p24.mov`
- Film 02 filename: `Film02_Appalachian_Son_1080p24.mov`
- Update Mac `STATUS.md` and copy the keeper/reject rows back into this repo on the next Mac-capable run.

## Explicitly out of scope for this cloud PR

Generating mp4s. Logging into Dreamina/Suno. CapCut export. Updating files under `/Users/.../Documents/Codex/` (not mounted).

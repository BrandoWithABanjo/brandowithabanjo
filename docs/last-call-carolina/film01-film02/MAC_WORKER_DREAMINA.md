# Mac worker — BrowserClaw / Dreamina runbook

**This cloud VM cannot do these steps.** BrowserClaw MCP on this run: `serverStatus: error`. No private worker. Dreamina is a logged-in browser on Brandon’s Mac.

Do **not** invent credentials. Use the existing Mac session. If a login wall appears, stop and wait for Brandon — do not type passwords from memory or chat.

## Endpoints (Mac localhost only)

| Service | Where |
|---|---|
| BrowserClaw / BrowserOS Neo MCP | `http://127.0.0.1:9210/mcp` |
| Dreamina (Seedance) | `https://dreamina.capcut.com/` (or the Mac’s usual Jimeng/Dreamina host) |
| CapCut web | CapCut Video Studio (same family as Aug 5 MV) |
| Codex Film 01 | `~/Documents/Codex/2026-08-12/film01-tech-intro-suno/` |
| Codex Film 02 | `~/Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/` |
| Pour reference | `~/Downloads/TwoDollarPour_MV_1080p24.mov` |

If Grok Bot is stuck on a macOS permission dialog: click Allow for Accessibility / Screen Recording / Local Network as needed so BrowserClaw can drive the browser. Do not reboot mid-Dreamina 4K job (jobs sit at 99% for minutes).

## BrowserClaw intent (when MCP is live)

1. Attach to the existing Chrome/BrowserOS profile that is already signed into Dreamina. **Never** create a new Google/CapCut account.
2. Navigate to Dreamina Seedance text-to-video (or image-to-video only when a **motion** plate exists — not a still).
3. Settings per hero take: **16:9**, duration **8–10s** (5s Mini only for blocking), model **Seedance 2.0** default; **2.5** only for F01-J/K aperture if 2.0 breaks the threshold.
4. Paste **one** prompt from this pack. Do not concatenate two shots.
5. Generate. Wait. Do not reload.
6. Download to the Codex `clips/` folder with the shot id in the filename.
7. Hide CapCut “feelgood” survey overlay if it eats clicks: `[class*="feelgood"] { display:none }`.
8. Export/download is often silent into `~/Downloads` — move the file immediately.

If BrowserClaw stays down, Brandon can paste the same prompts manually. The prompts are written for that.

## Download recipe-v2 first

Queued jobs may already be sitting in Dreamina history.

```bash
DEST="$HOME/Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/clips/recipe-v2"
mkdir -p "$DEST"
# After browser download:
# mv ~/Downloads/<dreamina>.mp4 "$DEST/S03_v2_exterior_truck.mp4"
# mv ~/Downloads/<dreamina>.mp4 "$DEST/S13_v2_wider_banjo.mp4"
```

Then run the five-frame strip from `QUALITY_BAR.md`. Update Mac `STATUS.md`:

- `S03 recipe-v2: PASS filename=…` or `FAIL reason=… next=fallback-A`
- `S13 recipe-v2: PASS filename=…` or `FAIL reason=… next=fallback-A`

## Generation order (credits)

1. QC queued recipe-v2 (spent already).
2. Film 02 remaining: S02, S04, S07, S08, S14, S15, S16, then S05, S06, S09, S10, S11, S12.
3. Film 01 F01-A, F01-J, F01-K (structure), then history modules B–I.
4. Mini 720p blocking only if a hero prompt is failing composition — not as timeline footage unless it passes Pour QA (usually it will not).

Do not batch two different shot jobs into one Seedance prompt. Batching multiple **separate** clips in one Dreamina chat is OK if the UI creates separate files (Aug 5 lesson).

## Prompt paste rules

- Prepend the film’s STYLE block verbatim.
- Include the NEGATIVES block verbatim.
- Set duration to the prompt’s `Duration` line.
- Attach **no** audio reference of the song (prevents lip-sync junk and extra music). Mute in CapCut anyway.
- Do not attach Brandon face photos.
- Chi: do not attach dog photos unless a dedicated Chi shot is later approved (none in this pack).

## After each take

```bash
ffprobe -v error -select_streams v:0 \
  -show_entries stream=width,height,r_frame_rate,nb_frames \
  -show_entries format=duration \
  -of default=nw=1 "$FILE"
```

Reject if duration ≈ 0, if frame count ≈ 1, or if r_frame_rate is a still. Then Pour QA.

## CapCut (only after a full spine)

See `film01/CAPCUT_ASSEMBLY.md` and `film02/CAPCUT_ASSEMBLY.md`.

Gotchas from the Aug 5 MV:

- Export button may download **silently** to `~/Downloads`.
- Chat-row clicks attach cards as chips.
- 4K jobs hang at 99% — wait.
- Build **one silent picture carrier** then drop the locked WAV once. Do not insert clips at time zero one-by-one if that caused Data errors before.

## Stop conditions

- Login wall / 2FA / captcha → stop, no credential invention.
- Dreamina out of credits → stop, log which shot was next.
- Second fail on the same close-hand or interior-glass recipe → switch to the wider/exterior fallback, do not burn a third identical fail.

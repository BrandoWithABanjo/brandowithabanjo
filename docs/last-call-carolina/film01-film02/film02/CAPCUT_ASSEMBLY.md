# Film 02 — CapCut assembly (2:52.091 / 1080p24)

Mac only. Do not start until S01 KEEP + S03 replacement + S13 replacement + remaining spine exist. **No Ken Burns hole-fill.**

## Project

- 1920×1080 · **24fps CFR** · rec.709
- Timeline length = **172.091s** (the locked WAV). Not 3:19.

## Audio

Import once:

`Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/audio/Appalachian_Son_APPLE_MUSIC_LENGTH_172s.wav`

- Do not use the 3:19 POCKET-LIFT song.
- Do not use Aug 5 `Brando_AppalachianSon_MV_Seedance_BEST.mov` as the audio bed.
- Mute all Seedance clip audio.
- No extra music, no VO.

## Picture spine (EDL)

| # | Shot | ~in | Source |
|---|---|---|---|
| 1 | S01 | 0:00 | **KEEP** `clips/S01_01.mp4` |
| 2 | S02 | 0:11 | new gen |
| 3 | S03 | 0:22 | **recipe-v2 exterior truck** if PASS, else fallback |
| 4 | S04 | 0:32 | new gen |
| 5 | S05 | 0:42 | new gen |
| 6 | S06 | 0:55 | new gen |
| 7 | S07 | 1:08 | new gen |
| 8 | S08 | 1:22 | new gen |
| 9 | S09 | 1:32 | new gen |
| 10 | S10 | 1:42 | new gen |
| 11 | S11 | 1:52 | new gen |
| 12 | S12 | 2:02 | new gen |
| 13 | S13 | 2:14 | **recipe-v2 wider banjo** if PASS, else fallback |
| 14 | S14 | 2:26 | new gen |
| 15 | S15 | 2:36 | new gen |
| 16 | S16 | 2:46 | new gen to 2:52.091 |

Snap ins to vocal/downbeat on the WAV. The table is a board, not sample-accurate.

Hard cuts. Physical matches (string, rail, sun, gravel) allowed. **No dissolves.**

## Handoff from Film 01

If a joint plate exists, S01 may start after a few frames of that plate. First committed step ~**0.40s**. Do not play Film 01 Suno under this timeline.

## Watermark / upscale

Same as Aug 5: if Mini 720p ever sneaks in, upscale + crop badge (2112×1188 → 1920×1080 @ offset). Prefer native 1080p gens so you are not finishing Mini as hero.

## End card (finishing only)

Optional last ~2s: gold serif `@brandowithabanjo` over S16 live hold. Type in CapCut, not in Dreamina. No legal name.

## Export

- `Film02_Appalachian_Son_1080p24.mov`
- H.264 high, 1080p24
- Mux locked WAV bit-identical (pcm_s24le 48k if that is the source)
- Duration must be 172.091s ± 1 frame
- Play back against Pour. If the cut feels like a slideshow, it is not done.

## Silent atomic carrier (if web timeline is flaky)

Decode keepers → crop badge → conform 24fps by frame duplicate/drop **not** optical flow → one silent 1920×1080 carrier of exact frame count → import once over the WAV. Same method as Film 01 v01 local conform, but **24fps** and **172.091s**.

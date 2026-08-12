# Film 01 — CapCut assembly (1080p24)

Do this on the Mac after keepers exist. Cloud VM cannot.

## Before import

1. Measure the locked WAV (see `LOCKED_AUDIO.md`). Write duration + sample rate into Mac STATUS.md.
2. `TAKE_PICK.md` is the cut authority. Slide picture to those cues; do not stretch the WAV.
3. Create a 1920×1080 **24fps** project. Not 30fps (v01 was 30; Pour and this rebuild are 24).

## Audio

- Import **only** `Film01_Tech_Shifts_3326a21e` WAV.
- Do not replace, fade, or loudness-match in CapCut.
- Mute every video clip’s audio (Seedance co-gen).
- Timeline length = WAV length. Picture may not run long or short.

## Picture order

| Track order | Module | Notes |
|---|---|---|
| 1 | F01-A | Must read as a real room, not Foundry |
| 2 | F01-B | Mill |
| 3 | F01-C | Rail |
| 4 | F01-D | Photography |
| 5 | F01-E | Radio |
| 6 | F01-F | TV |
| 7 | F01-G | Y2K |
| 8 | F01-H | MP3 |
| 9 | F01-I | AI + human tokens |
| 10 | F01-J | String → aperture |
| 11 | F01-K | Carolina hold = Film 02 frame 0 |

Hard cuts or physical match cuts only. **No crossfades, no film dissolves, no flash frames.**

If a module is 10s gen and the cue is 16s: overlap two **different** native-motion takes of the same chapter (second take continues the L→R carrier). Do not speed-ramp a 10s clip to 16s if it reads as a still at the ends. Do not freeze-frame.

## Watermark

If CapCut/Dreamina “Ai” badge is in a corner: scale/crop in the carrier (asymmetric zoom, e.g. 2112×1188 → 1920×1080) **after** QC, not instead of QC.

## Joint seam

Last 8–10 frames of F01-K should be the live hold. Export a PNG of the final frame for Film 02 editor. Film 02 clip 1 must start on that image’s world (S01 hollow truck may be the first *motion* of Film 02 if the hold is a still-adjacent live plate — but S01 cannot contradict the aperture geography). Prefer: F01-K ends looking down the gravel road; S01 is the hollow truck already on that road or departing a holler consistent with that light.

## Export

- Filename: `Film01_Tech_Shifts_v02_1080p24.mov`
- 1920×1080, 24fps CFR, H.264 high, rec.709
- Audio: the locked WAV muxed (pcm_s24le 48k if that is the source)
- Verify duration matches WAV to < 1 frame
- Do not upload until Pour QA on the **cut**, not just per clip

## Do not

- Overlay narration, lyrics, or “Layer 1/2/3” labels
- Use v01 174.8s WAV
- Start Appalachian Son under the prologue
- Ken Burns any failed chapter as coverage

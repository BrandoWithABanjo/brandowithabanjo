# Locked audio (Mac paths) — do not substitute

All paths are on **Brandon’s Mac**. This cloud workspace does not contain the WAVs. Durations below are the locked production numbers from the 2026-08-12 Codex handoff plus the Aug 2026 True-Final Masters Manifest.

## Film 01 — LOCKED

| Field | Value |
|---|---|
| Role | Prologue soundtrack. Only audio in Film 01. |
| Codex dir | `/Users/brandom5macpro/Documents/Codex/2026-08-12/film01-tech-intro-suno/` |
| Audio dir | `…/audio/` |
| Primary | **`Film01_Tech_Shifts_3326a21e`** (WAV) |
| Duration | **~180.88s** (~3:00.88) — measure exact sample count on Mac before CapCut lock |
| Cue authority | `TAKE_PICK.md` in that Codex folder (**written, locked**) |
| Generator audio | Mute every Seedance/Dreamina clip |

### Film 01 decoys — do not use

| Decoy | Why |
|---|---|
| Suno `0f95adb9-2f54-40f4-a272-6e16e0d05715` / `F01 FULL 10 - MAX SEPARATION.wav` (174.800000s) | Previous v01 winner. Superseded by `3326a21e`. Keep as picture-timing reference only. |
| Film 01 Extended 422.1s | Quarantined. |
| Unified rebuild 594.166s | Quarantined. |
| Any Seedance co-generated score | Mute. |

v01 picture master (comparison only, 30fps, 174.8s):

`/Users/brandom5macpro/Documents/Codex/2026-08-09/now/outputs/2026-08-09 - Film 01 Prologue - YouTube Master - v01.mp4`

SHA-256 (v01): `7dc76d8b14a11020b7efff6712221dd88f51be5afc832d4938d9867682fd1389`

New Film 01 **exports 24fps** to match Pour, even though v01 was 30fps.

## Film 02 — LOCKED

| Field | Value |
|---|---|
| Role | Appalachian Son picture lock. Apple Music length. |
| Codex dir | `/Users/brandom5macpro/Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/` |
| Working WAV | `…/audio/Appalachian_Son_APPLE_MUSIC_LENGTH_172s.wav` |
| Duration | **172.091s = 2:52.091** |
| Source family | Final Copy **Deep-Floor+** trimmed/conformed to Apple length |
| SHA-256 (Deep-Floor+ family, Notion Film 01 page) | `08f8ee798209f0cae214f1535e47acc75e097ce680778ae6aa9546ec431325cb` — **re-hash the 172s working file on Mac**; do not assume the trim kept the same hash |

Canonical Apple-length fact (True-Final Masters Manifest, corr 0.99995 vs Apple preview):

- Track 2 **Appalachian Son** Apple length **2:52.091**
- Filename family: `Appa-LATCH-un Son [byars MASTER Slap-Mid 7.7.26] [fade-in+tail].wav`

The 2026-08-12 rebuild explicitly locked a Deep-Floor+ copy **at that Apple length**. Use the Codex 172s WAV for CapCut. If a hash mismatch appears vs the Slap-Mid Apple file, **stop and compare both to Apple** — do not silently switch to the 3:19 song.

### Film 02 decoys — never mux

| Decoy | Duration | Why |
|---|---|---|
| `Appalachian Son [byars MASTER Car-Punch POCKET-LIFT 7.7.26 …].wav` | **3:19.784** | **Different unreleased song.** The Aug 5 Seedance MV used this by mistake (corr 1.00000 to that WAV). |
| `Brando_AppalachianSon_MV_Seedance_BEST.mov` audio | 3:19.79 | Same wrong song. Picture may be mined for camera ideas only; do not conform to it. |
| `AppalachianSon_HERO_LyricVideo/audio/Appalachian_Son_MASTER.wav` | review variant | corr 0.98440 vs Apple — not the stream. |
| June-11 Fable5 bounce on Drive | old | Archived. |

**Rule:** released Film 02 is **2:52**. Anything named plain “Appalachian Son” that runs **3:19** is the other song.

## Pour reference (picture bar, not the album bed)

`~/Downloads/TwoDollarPour_MV_1080p24.mov`

Album audio for Two Dollar Pour is a different track (Apple 3:09.819). Do not mux Pour audio into Film 01/02. Use the **mov** as motion/grade/finish reference only.

## Mac measurement commands (run on the Mac)

```bash
# Film 01
ffprobe -v error -show_entries format=duration,sample_rate -of default=nw=1 \
  "$HOME/Documents/Codex/2026-08-12/film01-tech-intro-suno/audio/"Film01_Tech_Shifts_3326a21e*.wav

# Film 02
ffprobe -v error -show_entries format=duration,sample_rate -of default=nw=1 \
  "$HOME/Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/audio/Appalachian_Son_APPLE_MUSIC_LENGTH_172s.wav"

shasum -a 256 \
  "$HOME/Documents/Codex/2026-08-12/film02-appalachian-son-rebuild/audio/Appalachian_Son_APPLE_MUSIC_LENGTH_172s.wav"
```

Write the exact sample count + SHA into Mac `STATUS.md` before CapCut lock. 24fps frame math:

- Film 02 172.091s × 24 = **4130.184** → conform by **sample-accurate audio length**, not by rounding picture to a whole second.
- Film 01 ~180.88s × 24 ≈ **4341.12** → same rule; snap to measured WAV.

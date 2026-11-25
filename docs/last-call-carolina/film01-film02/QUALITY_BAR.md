# Pour QA rubric

Reference master (Mac): `~/Downloads/TwoDollarPour_MV_1080p24.mov`

Sit the candidate full-screen. Play Pour, then the candidate, then Pour again. If a civilian would clock the candidate as “AI slideshow,” it fails.

## Gate 0 — would this survive?

Would this shot survive in a cinema-bar playlist if **nobody knew AI was involved**?

If you have to explain the shot, it fails.

## Gate 1 — motion (automatic fail)

Play at 1×, then scrub.

| Check | PASS | FAIL |
|---|---|---|
| Native motion | Subject and/or camera move continuously inside the generated frames | Still photo, Ken Burns push, looped 2-frame jitter, slideshow |
| One move | One readable camera intention (dolly, track, pan, handheld walk) | Whip-cuts inside the gen, random orbit, morph |
| Shutter | 24fps motion blur, cinema weight | Hyper-crisp video-game frames, soap-opera 60fps look |
| Optical flow | No warping at edges, no melting ground | Background smear, road taffy, truck dissolving |

Extract frames at 0%, 25%, 50%, 75%, 100%. If three of five frames are the same composition, **FAIL** (Ken Burns).

```bash
# Mac — five-frame strip
f="$1"
d=$(ffprobe -v error -show_entries format=duration -of csv=p=0 "$f")
for p in 0 25 50 75 99; do
  t=$(python3 -c "print(max(0, min($d-0.04, $d*$p/100)))")
  ffmpeg -y -ss "$t" -i "$f" -frames:v 1 "/tmp/qc_${p}.png"
done
open /tmp/qc_0.png /tmp/qc_25.png /tmp/qc_50.png /tmp/qc_75.png /tmp/qc_99.png
```

## Gate 2 — anatomy / materials (automatic fail)

| Check | PASS | FAIL |
|---|---|---|
| Hands | Stable bone count, plausible fingering or **hands not hero** | Melting, extra fingers, guitar-hand soup (S13 class) |
| Faces | If any extra is in frame: living skin, consistent identity | Mannequin, wax, plastic (S03 class) |
| Glass | Empty or honest reflections, no driver mannequin | Rearview face that is a doll |
| Instruments | Banjo is a 5-string object that keeps shape | Neck rubber, extra pegs, morphing headstock |
| Vehicles | Truck stays a truck for the whole clip | Body panels crawling, wheels sliding |

## Gate 3 — Chi (if present)

| Check | PASS | FAIL |
|---|---|---|
| Breed | Carolina dog / American dingo: lean, pricked ears, fishhook tail, gold coat | Lab, shepherd, husky, floppy ears, straight tail |
| Persistence | Same dog all five frames | Breed drift mid-clip |

**If any doubt: omit the dog.** Film 01 must not include her.

## Gate 4 — cinema (Pour match)

Pour look: tactile, amber practicals, real haze, 1080p24, no on-frame telemetry baked into pixels, no CGI satellite labels.

| Check | PASS | FAIL |
|---|---|---|
| Grade | Warm amber + natural shadow, filmic | Neon cyberpunk, HDR plastic, teal-and-orange Instagram |
| Materials | Worn wood, clay, oxidized paint, cloth | Perfect CGI showroom |
| Text | No readable signage in the gen | Fake neon words, melting letters, HUD |
| Identity | Castless / back / hands / silhouette | Generated Brandon face, celebrity, logo lockup |
| Audio | Will be muted | (Ignore gen audio; do not keep it) |

## Gate 5 — story job

Each prompt has **one job** and **one endpoint**. If the clip is pretty but does the wrong job (S03 that never shows a ridge receding; S13 that never shows a banjo), FAIL even if anatomy is clean.

## Retake policy

- **One** corrected retake for a hard fail, with the prompt narrowed (wider lens, fewer hands, exterior not interior).
- Second fail → change the recipe class (see recipe-v2 fallbacks), do not grind the same close-up.
- Do not retake for a harmless blurred label.

## Conform notes (not a reason to keep a bad take)

CapCut “Ai” badge: crop in assembly (asymmetric zoom), same as the Aug 5 Appalachian Son MV. That is finishing, not QC. A Ken Burns clip with the badge cropped is still a Ken Burns clip.

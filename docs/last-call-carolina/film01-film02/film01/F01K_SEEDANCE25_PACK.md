# F01-K — Seedance 2.5 single-attempt pack (Fable 5, 2026-08-13)

> **DO NOT RUN — SPEND FREEZE (Brandon/CoS, 2026-08-13).** No Dreamina generates. The existing F01-K candidate is NOT KEEP: hold the file, do not retake. This runbook is parked and only becomes actionable if Brandon explicitly lifts the freeze.

One careful 2.5 attempt beats ten 2.0 bot submits. This file is the whole runbook for that one attempt — when unfrozen.

## Why this runs on the Mac, not the cloud

Verified from the cloud VM on 2026-08-13 with a real Chrome window (not scripted JSON-RPC): `dreamina.capcut.com` loads, no region block, no captcha — but the browser is signed out and generation is gated on login. No Dreamina/CapCut credentials or session exist in the cloud environment, and the BrowserClaw MCP connection is down from this VM. So the generate must happen on a machine signed into Brandon's Dreamina account (the Mac).

## Settings (no deviation)

| Setting | Value |
|---|---|
| Model | **Seedance 2.5** — confirm the selector says 2.5 before pasting. 2.0 is below the bar and its K jobs charged without delivering. |
| Resolution | 1080p |
| Duration | 10s (8s acceptable if 10 is unavailable at 2.5) |
| Aspect | 16:9 |
| Attempts | **One.** No retry without reading the failure first. |

## Anti-bot posture

Dreamina may flag CDP/BrowserClaw/scripted sessions. Use a normal browser window, real mouse clicks, and human-paced typing or a single paste into the prompt field. If one browser path errors at submit, switch browsers (Chrome → Safari/Firefox) before concluding the job itself failed — but a browser switch is not a license for a second charged generate.

## The one attempt, in order

1. Confirm signed in as Brandon and note the credit balance (last known ~1.8K).
2. Set model 2.5, 1080p, 10s, 16:9. Re-check the model selector after any page reload — it can silently reset.
3. Paste the block below as one prompt. Generate **once**.
4. If the job errors or vanishes in-feed: **stop.** Screenshot the feed + credit balance and append a row to `Documents/Codex/credits-refunds/LEDGER.md` (date, job, model, credits before/after, error text) for the refund case. Do not resubmit.
5. If it completes: download, then QA before celebrating (gate below).

## Paste-ready prompt (one block)

Photoreal cinema, native 24fps motion blur, shot as if 35mm spherical anamorphic-adjacent but 16:9 full frame, restrained late-1980s industrial thriller, cyan shadow on camera left, warm amber practicals on camera right, tactile materials (black steel, oxidized copper, worn wood, glass, paper, rail, cable, string), continuous single camera move, real atmospheric haze, no CGI look, no text, no watermarks, no readable signage, no logos, no HUD, no title cards, no UI walls. Camera crosses the same aperture; the string line becomes a fence wire then a gravel road edge on red clay, Blue Ridge mountain light, natural depth and air, no people in the first seconds, then a distant anonymous figure far down the road (back only, tiny in frame). Slow dolly forward, no boom into sky, no drone telemetry. Hold the last 2 seconds as a near-static live plate (micro-wind in grass still moving — not a freeze). End on that plate: this is Film 02 frame 0. No boot stomp, no title, no dog, no close face. No Ken Burns, no still photo, no slideshow, no freeze frame, no morph, no portal, no particles, no holograms, no robots, no cyberpunk city, no liquid metal, no extra fingers, no melting hands, no mannequin skin, no wax faces, no generated celebrity, no recognizable living musician face, no dog, no Carolina dog, no pickup truck hero, no Tesla, no dashcam, no on-screen captions, no subtitles, no fake newspaper headlines you can read, no wrench-as-magic-key, no valve-as-portal.

## Pour QA gate (all must pass)

- `ffprobe` shows native video, not a stretched still; five extracted frames show different camera/subject positions.
- Continuous native motion — no Ken Burns, no freeze; the end hold still has micro-wind in the grass.
- No people close enough to melt; the distant figure is back-only and tiny.
- No portal language, no readable text anywhere, end plate usable as Film 02 frame 0.

Pass → K is a keeper; file it on the Mac `STATUS.md` and the repo board. Fail → stop and report to Brandon with frames; do not spend a second generate deciding alone.

## What stays frozen

- **F01-A:** hold the existing file (NOT KEEP: fake script, smeared hand, disembodied hand). No second A unless Brandon says.
- **F01-J:** recipe rejected (wrong job, portal ending, melt). Do not retake as written; new J strategy needs Brandon.
- **F01-B–I:** do not start until the A/J/K strategy is resolved with keepers.
- **Film 02:** paused.
- **Audio:** locked — `Film01_Tech_Shifts_3326a21e-be14-4ef6-b8e9-e8f565e0556f.wav`, ~180.88s. CapCut master muxes to this, then Google Drive share link. Not the Aug 9 v01, not a clip dump.

# Reel Studio

An agent skill that plans, builds, checks and renders short vertical videos (Reels, Shorts, TikToks) entirely from code: kinetic type, mask reveals, shape-carried transitions, a pendulum wipe, a torch reveal, step timelines, end cards and an original synthesised soundtrack locked to the beat.

It gives the agent a workflow (brief, direction card, beat sheet, build, sound, check, render, hand-off), two tested engines, and scripts that turn a video into things an agent can inspect: stills, contact sheets, QA numbers and loudness readings.

## Install

**Claude (app):** zip the `reel-studio` folder so that `reel-studio/SKILL.md` is inside, then Customize, Skills, Create skill, Upload a skill. Turn on Code execution and file creation in Settings, Capabilities.

**Claude Code:**
```bash
git clone https://github.com/vybavlakshmi/reel-studio ~/.claude/skills/reel-studio
```

Other agents that read `SKILL.md` folders can use it by copying the folder into their skills directory.

## Use
Ask for a reel. For example: "Make a 15-second reel for my coffee shop, comment keyword BEANS." The agent asks only what it cannot infer, shows a beat sheet, waits for your yes, then builds, checks its own frames and renders.

## Requirements
Node 22+, ffmpeg, Python 3.9+ with numpy, scipy and Pillow, and a Chromium-family browser. Playwright is needed only for the HTML engine. Run `bash scripts/check_env.sh` to see what is missing.

## Two engines
- **Remotion** (`templates/remotion-starter`): React components, quick to author. Remotion has its own licence terms; check them before commercial use.
- **HTML + Playwright + ffmpeg** (`templates/html-engine`): one file, no framework, frame-exact, real sub-frame motion blur.

## What is inside
```
SKILL.md                     the workflow the agent follows
references/                  editing rules, effects, engines, sound, QA, reference matching, small machines
scripts/                     env check, browser finder, render, stills, contact sheet, QA, sound synth, mastering, export
templates/remotion-starter/  tested starter project (seven-second demo)
templates/html-engine/       tested HTML page template
templates/cues.example.json  cue sheet matching the Remotion demo
```

## Tested on
A headless Linux sandbox (1 core, Node 22, ffmpeg 6.1, Chromium 141). See `references/cloud-linux.md` for measured timings.

## Credits and licence
MIT. See `LICENSE` (put your own name in it) and `NOTICE.md` for the work this builds on.

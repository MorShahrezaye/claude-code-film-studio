# Production Brief — The Multiplane Camera

Studio production brief · single run · self-contained · multiplane-camera · brief version 3.1

---

## 0. How to read this brief

This document is a complete production order for one short film and its companion cuts. You are the production studio: in sequence you act as researcher, director, production designer, cinematographer, technical director, compositor, sound designer, quality-control lead and reviewer.

**The bar.** This film will be judged against the most striking moving images being made anywhere: feature-film title sequences, cinematic game trailers, the best real-time graphics demos, and the work of the leading artists who make images with code. The art rubric in §6.10 stops at 10 only because a scale needs an end; aim past it. Wherever this brief is silent, the answer is the more ambitious one that you can still finish, verify and deliver.

**Time.** The whole production has 4 to 8 hours: aim to finish in about 5 to 6, and treat 8 hours after `started_utc` as a hard limit. Plan the run in `plan.md` before you build anything and adapt the plan at every stage — measure, re-project, and cut scope by the ladder of §10.12 when it runs long (§10.1). Ideas are reviewed while they are cheap — as a written plan, as still frames, as short clips — and the full masters are rendered once, at the end. A true and beautiful film delivered in six hours beats a perfect one that is never finished.

**Two layers.** The **fixed layer** is short and exact: the science (§7.2, §7.3, §7.5, §7.6), the captions and timecodes (§6.5, §8), the series signature (§6.3), legibility and safety (§6.4, §6.6), honesty (§6.9), the deliverables (§3) and the automated checks (§12). Everything the viewer looks at and listens to is the **designed layer**, and it is yours: the world, its light and materials, the style, the palette, the lenses, the shots and cuts, the staging of the payoff, the transitions, the typography's placement and backing, the sound design. §7.4 gives a creative brief for this film — the heart of it, the image that must land, and a few sparks — not a blueprint. A film that is correct but looks like the default output of a rendering library has failed this brief as surely as one with a wrong number on the receipt.

**Reference library.** A folder of research excerpts accompanies this brief at `<BRIEFS>/reference/` (if it is not there, look for a `reference/` folder next to this file). Read its `INDEX.md` in Stage 0 and the concept's entry in `reference/concepts/`. Before and during look development, read `reference/craft/`: how great films and animations build depth, light, texture, rhythm and wonder, and how the strongest visual creators pace, cut and score. Use it to raise your bar and to find ideas no default renderer would produce; never copy a named work's look. The brief always prevails; the library never adds facts to the film.

**One pass, no questions.** This production is completed from start to finish in a single pass with no outside input: nothing is asked of anyone, no confirmation or approval is awaited, no options are offered for someone else to choose. Every choice this brief does not fix is a designed-layer decision, made through the treatment, look development and reviews of §10.5–§10.7 and recorded in `decisions.md`. Nothing is escalated except through the BLOCKED protocol of §14.5, which ends the run after its file is written.

**Tools.** Use any language, library or program that runs on this machine: Node, Python 3, GLSL, WebGL2 and Three.js, a Python-scriptable 3D suite, ffmpeg, numerical libraries. Create virtual environments and install what you need from npm or PyPI; record every package and version in `run.json`. §6.1 fixes only the interfaces and guarantees (truth, determinism, capture quality, text), and Appendix A gives a verified reference pipeline that you may use as it is, extend, or replace. Nothing is handed to you as code; you write all of it.

Vocabulary: **must** = mandatory; **never** = prohibited; **record** = write to the named file in the run directory. "Frame" always means a rendered image at a fixed integer index `i`, with time `t = i / 60` seconds. "P" = portrait master, "L" = landscape master, "S" = square master, "LP"/"LS" = portrait and square loops. "Hero" = the accent that marks the payoff element (§6.3).

---

## 1. Introduction

This brief produces a short film about the multiplane camera: one painting split across seven sheets of glass hung at different distances beneath a camera. Move the camera and the sheets slide across the picture at different speeds — the nearest fastest, the farthest slowest — and a flat painting becomes a deep world. The film opens inside that world, shows what one flat painting would do instead, lets the depth play, and at the payoff steps outside the rig to reveal seven flat panes of painted glass hanging in the dark. Everything is computed: the paintings, the glass, the rig and the light.

The finished piece is a computed film: nothing in it is drawn by hand, keyframed by eye, or taken from stock. Every image is produced by code that implements the mathematics of §7 — built into a world, lit and photographed with intent — and every number shown on screen is measured from that code while it runs. The tone is quiet, precise and full of wonder: no hype words, no exclamation marks, no jokes, no calls to the viewer to do anything. The film works by letting the phenomenon happen in front of the viewer in a world worth looking at, by stating its one rule plainly, and by proving on screen that the rule was followed.

---

## 2. The ambition

Produce the complete deliverable set of §3 for the concept of §7 within the time budget of §10.1, with every check of §12 passing, the three art-panel reviews and the final look of §13, and a finalized run directory as specified in §14. What excellent means here, in priority order:

1. **True.** The tests of §7.5 pass with margin; every number on screen is measured; a reviewer who did not build the piece can re-derive every claim.
2. **Unforgettable.** One image — the moment named in §10.5 — that a first-time viewer would describe to someone afterwards. The payoff is the film's spectacle.
3. **Beautiful in every frame.** Light, depth, material, composition and motion that a leading motion-design studio would sign; every hero frame aims at 8.5 or above on the art rubric of §6.10, and within the time plan the studio keeps pushing while a better idea exists.
4. **Legible.** Every caption reads at one quarter of the frame size with the sound off.
5. **Seamless.** The loops loop invisibly; P, S and L end on their own first frame.
6. **Reproducible.** Two independent renders of the same frame agree within the tolerance of §12.

---

## 3. Expected output

All paths are relative to the run directory `RUN` defined in §4.

| # | File | Spec |
|---|------|------|
| 1 | `deliverables/multiplane-camera_P.mp4` | 1080×1920, 60.000 fps, exactly 2700 frames (45.000 s), H.264 High, yuv420p, bt709 tv range, AAC 192 kb/s 48 kHz stereo, loudness −14 LUFS ±1, true peak ≤ −1.0 dBTP |
| 2 | `deliverables/multiplane-camera_L.mp4` | 1920×1080, 60.000 fps, exactly 5400 frames (90.000 s), same codec and audio spec |
| 3 | `deliverables/multiplane-camera_S.mp4` | 1080×1080, 60.000 fps, exactly 2700 frames (45.000 s), same codec and audio spec |
| 4 | `deliverables/multiplane-camera_LP.mp4` | 1080×1920 seamless loop, 60.000 fps, exactly 480 frames (8.000 s), periodic audio |
| 5 | `deliverables/multiplane-camera_LS.mp4` | 1080×1080 seamless loop, same frame count and audio rule as LP |
| 6 | `deliverables/multiplane-camera_poster_P.png`, `_poster_L.png`, `_poster_S.png` | PNG, sRGB, exact master dimensions, the poster frame of §8.4 with the poster caption |
| 7 | `deliverables/multiplane-camera_poster_P_clean.png`, `_poster_L_clean.png`, `_poster_S_clean.png` | Same frames, no text |
| 8 | `deliverables/manifest.json` | Schema in §14.1 |
| 9 | `deliverables/README.md` | Plain-language summary per §14.2 |
| 10 | `qa/qa_report.md`, `qa/probe_*.jsonl` | Every check of §12 with measured value, threshold, pass/fail; the per-frame probe records |
| 11 | `reviews/review_1/`, `review_2/`, `review_3/` (the four reviews and their evidence), `reviews/review_N_notes.md`, `reviews/final_look.md` | The art panel's reviews of the plan, the look and the motion, with the disposition of every change, and the final look (§13) |
| 12 | `build/beats_P.json`, `build/beats_L.json` | The beat sheets of §8, copied verbatim |
| 13 | `build/metrics.json`, `build/events.json` | Per-frame metrics and sound events from the bake (§10.2) |
| 14 | `qa/contact_P.png`, `qa/contact_L.png`, `qa/contact_S.png`, `qa/frames/*.png` | Contact sheets and fixed-timestamp frames used as review evidence |
| 15 | `plan.md`, `decisions.md`, `open-items.md`, `postmortem.md` | The living time plan (§10.1) and the process records of §14 |
| 16 | `lookdev/` | The look-development record of §10.5–§10.6: the treatment, every iteration's hero frames, critiques and scores, the selection |
| 17 | `build/look.json` | The designed values the renderer reads (world, palette, light, materials, lenses, shot list per format, transitions, the turn, the hero accent) |

A run is complete only when every row exists, `qa/qa_report.md` shows every check PASS or failed-with-explanation (each such check has a `decisions.md` entry and an `open-items.md` row, §12), and the final look of §13.4 is written — or when the 8-hour limit of §10.1 ended the run with every deliverable present and everything unfinished listed in `open-items.md`.

---

## 4. Where to store things

Base directory (fixed): `<OUTPUT>/`

Run directory: `RUN = <OUTPUT>/multiplane-camera/run-<YYYYMMDD-HHMMSS>/` where the timestamp is the UTC start time of this run, taken once at the beginning (`date -u +%Y%m%d-%H%M%S`) and never changed. Create it with `mkdir -p`. If the base directory is not writable, stop and follow §14.5. Never write outside `RUN` except for the package caches that npm, pip and Playwright manage themselves; scratch files go under `RUN/tmp/`.

Layout inside `RUN` (create all folders at the start):

```
RUN/
  run.json            # start time, host, tool versions, renderer string, seed, brief version
  plan.md             # the time plan: planned and actual time per stage, re-projections, scope cuts (§10.1)
  decisions.md        # every judgment call, with the reason (append-only; headings carry `date -u` time)
  open-items.md       # anything unresolved that needs the project owner's decision
  postmortem.md       # 5 things that went right, 5 that went wrong, the timing table
  src/                # simulation, world, text layer, page(s), shaders
  tools/              # bake, render driver, QA and helper scripts
  audio/              # synthesis, generated assets, stems, mixes
  assets/fonts/       # Archivo[wdth,wght].ttf
  build/              # beats_*.json, metrics.json, events.json, look.json, baked state, animatics
  lookdev/            # treatment.md, iter_1 … iter_N/, selected.md
  renders/            # intermediate video-only renders, identity files and per-segment logs
  qa/                 # qa_report.md, probes, contact sheets, frames/, determinism/
  reviews/            # review_1 … review_3/ (reviews and evidence), review_N_notes.md, final_look.md
  deliverables/       # final files only
  tmp/                # scratch
```

File naming: lower-case, words separated by `_`, no spaces, no dates in deliverable names. Final files are exactly the names in §3.

---

## 5. Prerequisites and pre-flight

Run these checks first and record the results in `run.json`. Fix what can be fixed; otherwise follow §14.5.

1. `node -v` v20 or later; `npm -v` works; `python3 --version` 3.10 or later with `python3 -m pip --version` working (a virtual environment under `RUN/.venv` is recommended).
2. `ffmpeg -version` and `ffprobe -version` 5.0 or later; `ffmpeg -hide_banner -encoders | grep -E "libx264|aac"` lists both; `ffmpeg -hide_banner -filters | grep loudnorm` returns a line.
3. Browser: `npm i playwright` then `npx playwright install chromium` (record versions). If the download fails, launch the system browser with `channel: 'chrome'` or the `executablePath` of the system's Chrome or Chromium; record which. If neither launches, follow §14.5.
4. GPU: launch headless Chromium with the flags of Appendix A.3 and read the WebGL2 renderer string (`WEBGL_debug_renderer_info`). Record it as `gpu_renderer`. If it names `SwiftShader`, rendering runs on the CPU: continue, and multiply the render estimates of §15 by three.
5. Font: copy `fonts/Archivo[wdth,wght].ttf` from the folder beside this brief to `assets/fonts/` and verify it: 658,596 bytes, SHA-256 `0e094a7d3c7c4c25cf1310c4b30014f1dae9332220b1c2c88f4fa996f0b05053`, SIL Open Font License 1.1. If missing or wrong, use `DejaVu Sans` (Bold) and record the substitution.
6. Generated-sound credentials (§9.3): the file `<CREDENTIALS_FILE>` contains one line `ELEVENLABS_API_KEY=<key>`. Read the key from that file at call time; never copy it into the run directory, a log, a manifest or a commit. Verify it with `GET https://api.elevenlabs.io/v1/voices` (header `xi-api-key`). Record `generated_sound_available: true|false` with the HTTP status. If the file is missing or the call fails twice, the generated tier is skipped and the Tier 0 mix of §9.1 is the final mix.
7. Network use is limited to the npm registry, PyPI, the Playwright browser CDN and the sound service's endpoint of item 6. Everything the film needs is in this brief, the `fonts/` folder and the reference library.
8. Machine: this is a laptop with an integrated GPU that is lost under heavy parallel load (§11.4). Check `free -g` (at least 8 GB available before any render), `df -h` (about 15 GB free for a full run), and that no other render is running (`pgrep -af "chrome|ffmpeg"`); if another production is rendering on this machine, wait for it to finish before starting yours.
9. Create `run.json` with: `brief: "multiplane-camera"`, `brief_version: "3.1"`, `started_utc`, `host`, `gpu_renderer`, `node`, `npm`, `python`, `ffmpeg`, `packages` (name and version of everything installed), `browser`, `generated_sound_available`, `font`, `seed: 20260928`.

---

## 6. Studio standards

### 6.1 Technology — what is fixed, what is free

Fixed interfaces and guarantees:

- **One source of truth.** The simulation of §7 lives in one module that both the bake and the renderer use, or the bake writes the per-frame state and the renderer only reads it. What the viewer sees is always the state the bake computed (gate B03). JavaScript engines in Node and in the browser do not return the same last bits for `Math.sin`, `cos`, `acos`, `log`, `pow`, `cbrt`, `exp` and `atan2`; a chaotic simulation run twice in two engines diverges within seconds. Use bake-and-replay (recommended for chaotic systems), or restrict the simulation to IEEE-exact operations (`+ − × ÷ sqrt`) plus portable implementations of any transcendental function, verified bit-identical in both engines (§11.2).
- **Frame-index time.** The whole picture and the text are a pure function of the frame index `i` and of the state at `i`. Never use wall-clock time, `requestAnimationFrame` timing, `Math.random`, or timers to drive anything visible. Randomness comes only from the seeded generator of Appendix A.1 (`mulberry32`, seed `20260928`), drawn in a fixed, documented order; shader noise hashes position and frame index.
- **Everything visible is computed in this run.** No external image, texture, model, environment map, video or font (other than Archivo): every surface, sky, texture and light is generated by code. Generated audio assets are allowed under §9.3.
- **Text is typeset, not painted.** Captions, readout and receipt are typeset in Archivo by the browser (DOM text) over the picture — live in the same page, or as a transparent overlay page composited over pre-rendered picture plates — so their rectangles can be measured (the probe of §12.0). Labels that belong to the world (a name on an object) may be part of the picture; they are then excluded from the text gates and must still read at 270 px.
- **Capture quality.** Each frame is rendered at 2× the delivered resolution (or with an anti-aliasing of equal or better measured quality, recorded) and downscaled once with Lanczos, converting to BT.709 limited range (`out_color_matrix=bt709:out_range=tv`). Every captured frame's identity is verified (§11.3, Appendix A.3).
- **Encoding.** libx264 High, `-preset slow -crf 17 -pix_fmt yuv420p -g 120 -keyint_min 60 -movflags +faststart`, bt709 tags, tv range; audio muxed separately (AAC 192 kb/s, 48 kHz, stereo).
- **Determinism.** Two independent renders of the same frame agree within 0.5/255 mean absolute difference (gate B02).

Free (designed, recorded in `build/look.json` and `decisions.md`): the rendering technology and techniques (WebGL2 with Three.js and custom GLSL, raymarched distance fields, GPU particle systems and simulations through render targets, procedural painting, volumetrics, a Python-scriptable 3D suite for plates if a 20-frame test proves it fits the budget, or a combination composited in ffmpeg), resolution strategy, anti-aliasing, motion blur (from fixed sub-frame offsets of `i` only), the post chain, and how segments are parallelized within the limits of §11.4. Appendix A gives a verified reference pipeline (Three.js with an HDR post chain on this machine's GPU, and a render driver with verified capture); use it, extend it, or replace it, and record why.

### 6.2 Formats

| Format | Pixels | Frames | Duration | Content |
|---|---|---|---|---|
| P | 1080×1920 | 2700 | 45.000 s | Beat sheet §8.1 |
| L | 1920×1080 | 5400 | 90.000 s | Beat sheet §8.2 (the beats of §8.1 from `open` to `replay` restaged for the wide frame, then the extended segment, then the receipt and return) |
| S | 1080×1080 | 2700 | 45.000 s | Beat sheet §8.1 restaged for the square frame |
| LP, LS | 1080×1920 / 1080×1080 | 480 | 8.000 s | §8.3 |

Frame `2700` of P and S does not exist; the last frame is 2699 and it must match frame 0 within the tolerance of §12. Each format has its own shot design: never letterbox, never pillarbox, never crop one master to make another.

### 6.3 The series signature (fixed)

These seven things make every film of this studio recognizable; everything else changes from film to film.

1. **The cold open.** The phenomenon is already moving on frame 0, in a finished picture, with the opening caption fully visible. No title card, no logo, no fade from black.
2. **The rule.** `The rule:` at exactly 2.000 s, then the concept's rule line (§8), in the rule-line style.
3. **The live readout.** A measured number tied to the phenomenon, visible from 2.000 s to the receipt, updating every frame.
4. **The payoff at 24.000 s.** The state change of §7 happens on frame 1440, held for 30 frames at the concept's hold speed (§7.3), and the payoff element carries the film's **hero accent**: one colour or quality of light reserved for it and used nowhere else before the payoff except as a glint of anticipation. The hero accent is chosen by the studio per film and recorded in `look.json`.
5. **The replay.** The payoff shown again from a second view (a different angle, distance or lens) with the caption `Again, closer.`
6. **The receipt.** The six-row card of §6.7 over the living scene.
7. **The return.** The film ends on its own first frame, so a player that repeats it shows no seam.

Typography is part of the signature: Archivo, sentence case, captions heavy (weight 700–800), the rule line one step lighter, the readout in tabular figures.

### 6.4 Text and legibility (fixed limits, designed style)

- Every caption, the readout and the receipt are DOM text in Archivo. The page loads the font and confirms `document.fonts.check('700 100px Archivo') === true` before frame 0; otherwise it aborts.
- Reference sizes (CSS px at 1×): caption P 78 / L 72 / S 70; rule line P 60 / L 54 / S 54; readout value P 44 / L 44 / S 40 with its label at about three quarters of that; receipt title / rule / body P 72 / 48 / 38, L 64 / 44 / 36, S 64 / 44 / 36; poster caption P 96 / L 88 / S 88. The designed size may differ from the reference by at most ±12 % and never falls below one quarter-scale legibility of 16 px for captions and 9.5 px for the readout value (gate D03).
- Caption budget: at most 8 words and 2 lines (the rule line: 12 words, 3 lines); one caption visible at a time; line breaks are written into the caption text of §8 as `\n` and the caption never wraps on its own (`white-space: pre-line`, gate D01). Each captioned beat `[t0, t1)`: the caption is fully visible from `t0 + 0.4` s at the latest until `t1 − 0.25` s at the earliest; entrance and exit are designed (fade, settle, write-on, light) and never longer than 0.4 s. The opening caption is fully visible on frame 0, and the `return` beat's caption stays fully visible to the last frame.
- Every character on screen is a glyph present in Archivo (Latin-1 plus `·`, `÷`, `→`, `°`, `–`, `—`).
- Text-safe areas (all text inside): P `x ∈ [54, 1026], y ∈ [300, 1560]`; L `x ∈ [96, 1824], y ∈ [54, 1026]`; S `x ∈ [65, 1015], y ∈ [65, 1015]`. Positions inside them are designed and constant across a master.
- Legibility is measured, not assumed: ink against what is behind it must reach a contrast of 4.5:1 (gate D04). Place text where the world is calm, or give it a designed backing (a feathered local darkening, a glass card, a band of shadow) that looks like part of the film.
- Text colour is a near-white or near-black chosen for the film; the receipt's source and credit rows are one step quieter.

### 6.5 The timeline skeleton (fixed)

| beat | P and S | L | what happens |
|---|---|---|---|
| open | 0.000–2.000 s | same | the cold open with the opening caption |
| ruleIntro, rule | 2.000–3.000, 3.000–8.000 s | same | `The rule:`, then the rule line |
| expect | 8.000–13.500 s | same | the naive expectation (§7.7), shown and then contradicted |
| run, run2 | 13.500–24.000 s | same | the system evolves toward the payoff |
| payoff, payoff2 | 24.000–32.000 s | same | the state change at frame 1440, held 30 frames |
| replay | 32.000–38.000 s | same | the payoff again from the second view |
| extended segment | — | 38.000–80.000 s | five cards explaining the mechanism with computed pictures (§8.2) |
| receipt | 38.000–43.000 s | 80.000–88.000 s | the receipt card over the living scene |
| return | 43.000–45.000 s | 88.000–90.000 s | back to the opening state; the last frame equals frame 0 |

Inside this skeleton the pacing, shots, cuts and transitions are designed (§6.6).

### 6.6 Picture language (designed, within safety limits)

- **Shots and cuts.** The film may be one continuous take or many shots. Cuts are allowed when they are motivated — on an action, on a musical beat, or to a new scale (a macro insert, a reveal) — at least 1.5 s apart, never inside the 30-frame payoff hold, and recorded in the shot list of `look.json`. A cut into a macro detail of the phenomenon, then back, is one of the strongest tools available.
- **Camera.** Lenses, focal lengths, depth of field, camera moves and rigs are designed. The camera may cut or move fast when the film wants energy; it never jitters, and a still frame of any shot must read as a composed image.
- **Light, world, style.** Photographic realism, painterly, graphic, macro, abstract light, or a style no one has named — any of them, executed at the highest level. The world has depth and air, motivated light, and secondary life that serves the phenomenon.
- **Tells of a default look, to be designed out:** unset or uniform materials; flat ambient light with no direction; a pure black void around the subject; a centred subject in every shot; one mark size for everything; uniform dots with no depth cue; library-default colours; motion without hierarchy; fog, bloom or grain used as a filter over everything instead of as light.
- **Safety.** No more than 3 luminance flashes per second (gate C01); no strobing patterns over large areas; text never over bloom-hot regions (gate D04).

### 6.7 The receipt card

Six rows over the living scene (which continues at the concept's receipt speed, darkened and softened so the card reads), on a designed backing. Each row is a DOM row that may wrap inside the card (`receiptLines` reports the six row strings):

1. Title: `The Multiplane Camera`
2. Rule: `The farther the pane, the slower it slides.`
3. Parameters: `7 panes · 0.50 m to 4.65 m · each 1.45× farther`
4. Check: `Checked: nearest ÷ farthest pane speed = <measured value>`, formatted as §7.5 states — read from `build/metrics.json`, never typed by hand.
5. Source: `W. E. Garity, US Patent 2,281,033, 1942`
6. Credit: `Every frame is computed from the rule above.`

### 6.8 Poster stills

For each master, render the poster frame of §8.4 twice: once with the poster caption only (`Seven flat panes.\nOne deep world.`, poster caption size; no beat caption, no readout) and once clean (`?notext=1`). Export PNG at the master's 1× dimensions (downscaled from the 2× capture with Lanczos, `-pix_fmt rgb24`). The poster frame contains the payoff element in the hero accent and is the film's single best image at 270 px wide.

### 6.9 Honesty

- Every number on screen is measured in the run. Never type a number the code did not produce.
- Every claim in a caption is the rule, a measurement, or a sourced fact of §7.1. Never add facts that are not in §7.
- Never describe anything as "proven" or "exact" unless §8 says so.
- The seed is fixed. Never search seeds or tweak parameters for a prettier result; if the specified behaviour does not appear, follow the fallback of §7.3 and record it.
- Beauty is added by world, light, material, camera, staging and sound — never by altering what the equations produced, hiding a frame, or hand-placing an element to fake the payoff.

### 6.10 The art rubric

Used in look development (§10.6) and by the art panel (§13). Each line is scored 0–10 with these anchors: **10** stands beside the best title sequences, trailers, real-time demos and art made with code; **9** a leading studio's finished work; **8.5** this studio's floor for a hero frame; **7** strong independent work; **5** programmer art: correct but unlit, unstaged, default; **3** the untouched output of a rendering library; **0** broken.

| # | line | what is judged |
|---|---|---|
| 1 | Wonder | would a stranger stop and look; is there something here they have not seen before |
| 2 | Light | direction, contrast, colour temperature, highlights that bloom where light is hot, shadows that anchor; nothing flat |
| 3 | Depth and air | foreground, subject and background separated by scale, haze, focus and light; the frame has air |
| 4 | Material | every surface reads as something — glass, stone, metal, water, paper, light itself; nothing reads as unset |
| 5 | Composition | one focal point; the eye knows where to go; balance and negative space; works at 270 px |
| 6 | Camera and cut | every shot has an intention; the angle and lens tell the story; cuts and moves land on something |
| 7 | Motion | the payoff is the largest change in the film; calm beats are calm on purpose; nothing moves without a reason |
| 8 | Legibility | captions and the readout read instantly; nothing important hidden by bloom, blur or clutter |
| 9 | Coherence | palette, light and style belong to one film across beats and formats |
| 10 | Truth made visible | the beauty comes from the phenomenon itself; the rule is visible in the picture, not only in the captions |

Be hardest on lines 1, 2, 3, 4 and 6, where default renders fail. A score is worth recording only with the sentence that justifies it.

---

## 7. The concept

### 7.1 What it is, and where it comes from

The multiplane camera stacks up to seven panes of painted artwork at different distances beneath a single camera. Because nearer layers sweep across the frame faster than distant ones for the same camera motion, the rig produces true depth parallax from flat art: a layer's on-screen displacement is inversely proportional to its distance (similar triangles). William Garity's patent for Walt Disney Productions describes the stack, its parallax and two further rules: a limit on how far a plane may be out of focus, and a balance of light in which each plane is lit so that every plane reaches the camera equally bright despite the light lost through the glass above it. Disney's rig was first used in The Old Mill (1937), which won the Academy Award, and throughout Pinocchio and Fantasia (1940); earlier multi-layer rigs were built by Lotte Reiniger and Carl Koch (1926) and by Ub Iwerks (1933). This film builds a seven-pane rig in computation, checks the parallax law on its own rendered frames, and prints on the receipt the measured speed ratio of the nearest and the farthest pane.

Sources (these are the only facts you may quote on screen):

- William E. Garity (assignor to Walt Disney Productions), "Method of Producing Animated Photoplays," US Patent 2,281,033, filed May 8, 1939, granted April 28, 1942 (full text at patents.google.com/patent/US2281033A).
- William E. Garity, "Control Device for Animation," US Patent 2,198,006, filed November 16, 1938.
- Wikipedia, "Multiplane camera": Disney's rig first used in The Old Mill (1937, Academy Award), then in Pinocchio and Fantasia (1940); earlier versions by Lotte Reiniger and Carl Koch (The Adventures of Prince Achmed, 1926) and by Ub Iwerks (1933).
- Quotable facts: up to seven panes of glass under one camera; near layers sweep across the frame faster than far ones; apparent displacement is inversely proportional to distance; each plane lit to balance the light lost through the glass above it; The Old Mill, 1937.

### 7.2 Mathematics and parameters (fixed)

**The rig.** A pinhole camera — the rig camera — at `c(τ) = (x(τ), y(τ), 0)` looks along `+z`. Seven panes of glass are the planes `z = d_k` with `d_k = 0.5 × 1.45^k` m for `k = 0 … 6`: 0.500, 0.725, 1.051, 1.524, 2.210, 3.205, 4.647 m (`d_6/d_0 = 1.45^6 = 9.2941`). Pane `k` carries a painting — colour and coverage on clear glass — as a function of pane coordinates `(u, v)` in metres. A point `(u, v)` of pane `k` appears in the rig camera's image at `f_px · (u − x, v − y)/d_k` from the image center (`f_px` = focal length in pixels), so a lateral camera move `Δx` slides pane `k` across the picture by `f_px Δx / d_k`: the speed is inversely proportional to the distance. That is the rule. The paintings (what they show, their style, how much of each pane is clear glass) are designed and computed in the run; the distances and the camera's path are fixed.

**The camera's path** (simulation time `τ`, `dt = 1/60`, `r = 1`; `τ = t + 1.6` outside holds): `y = 0`; speed `V = 0.05 m/s` for `τ < 15.1` (master 13.5 s); `V = 0.05 + 0.05 · easeInOutCubic((τ − 15.1)/2)` for `15.1 ≤ τ < 17.1`; `V = 0.10 m/s` after. Closed form, with `F(u) = u⁴` for `u ≤ ½` and `(u − ½) + (2 − 2u)⁴/16` for `u > ½` (the integral of easeInOutCubic): `x = 0.05 τ` for `τ ≤ 15.1`; `x = 0.755 + 0.05 (τ − 15.1) + 0.1 F((τ − 15.1)/2)` for `15.1 ≤ τ ≤ 17.1`; `x = 0.905 + 0.10 (τ − 17.1)` after. Reference: `x` = 0.080 m at master frame 0, 0.480 m at frame 480, 0.905 m at master 15.5 s, 1.755 m at the payoff frame. The rig camera's focal length, field of view and aperture are designed per format; its focus distance is designed except in L `how3`.

**Glass and light.** Each pane of clear glass transmits `T = 0.92` of the light that passes through it, so the rig camera sees pane `k` through `k` panes: attenuation `T^k` (0.606 for the farthest). The light is balanced as the patent describes: pane `k` is lit `T^(−k)` times brighter (1.649 for the farthest), so every pane reaches the camera equally bright. L `how4` switches the balance off and on again.

**Depth of field.** With the rig camera focused at distance `s` through an aperture of diameter `A`, a point of pane `k` blurs to a disc of diameter `c_k = A · f_px · |1/s − 1/d_k|` pixels (thin lens). Any defocus the rig camera shows follows this law; L `how3` demonstrates it.

**The flat print** (the expectation device, frames 480–809): the seven paintings composited into one flat image exactly as the rig camera saw them at frame 480, extended by the same composite to cover the camera's travel through the beat, laid on a single pane at the middle distance `d_3 = 1.524 m` and photographed by the rig camera in place of the stack; every part of it therefore slides at the one speed of `d_3`, as a single flat painting would.

**Metrics per frame:** `speed_near`, `speed_far` = the angular speed of pane 0 and pane 6 across the rig camera's view in degrees per master second, `(180/π) × V × timeScale / d_k` (during the flat print both use `d_3`); `x_cam`; `focus_m`; `far_gain` (the farthest pane's light factor). Reference: 5.7 and 0.6°/s at 0.05 m/s; 11.5 and 1.2°/s at 0.10 m/s; 1.9°/s for both during the flat print.

```json
{"seed": 20260928, "panes": 7, "d0_m": 0.5, "depth_ratio": 1.45, "glass_T": 0.92, "light_balance": true,
 "V0_m_s": 0.05, "V1_m_s": 0.10, "ramp_tau": [15.1, 17.1], "flat_pane": 3, "flat_frames": [480, 810],
 "loop_radius_m": 0.03, "event_step_deg": 4, "dt": 0.016666666666666666, "r_min": 1, "r_max": 1, "PREROLL": 96}
```
`PARAMS` exported by the simulation module must equal this object (gate H02). The seed drives only the calibration textures of test 4.

### 7.3 Simulation procedure, time mapping and fallbacks (fixed)

The first six paragraphs are the same in every film of this series; the rest is this film's own.

**Clock and accumulator.** The simulation advances in integer steps. The base rate `r` is a number of simulation steps per rendered frame (it may be fractional; this film's value, or the bake that finds it, follows below). Advance with an accumulator: `acc += r × timeScale(frame); while (acc ≥ 1) { step(); acc −= 1; }`, where `timeScale(frame)` is 0.25 during the 30-frame payoff hold (frames 1440–1469), 0.5 during the replay beat, and otherwise the beat's `timeScale`. The accumulator starts at 0 at pre-roll frame 0 and is part of the state that `renderFrame(i)` rebuilds when it rewinds. `simTime` in the probe is `steps × dt`.

**Between steps.** Whenever `r × timeScale < 1`, some frames take no step, and yet the picture never freezes (gate C03). Continuous quantities are drawn at the fractional time `(steps + acc) × dt`: closed-form systems evaluate their formulas there; stepped systems draw `state(n) + acc × (state(n+1) − state(n))`, where `state(n+1)` comes from stepping a copy (the copy is discarded; the real step happens when `acc` reaches 1); discrete systems draw the fractional phase this film defines. Interpolation is for drawing only: metrics, events and tests use the stepped states.

**Pre-roll.** Frame 0 of every master shows the state after `PREROLL = 96` frames of stepping at rate `r` with `timeScale = 1`, with every history (trails, ribbons, accumulators) built, so frame 0 carries 96 frames of history. All timecodes of §8 are master frames; the pre-roll is the 96 frames before frame 0.

**Clocks.** Schedules written in master time are evaluated at `t = frame / 60` on frames 0–1919 and from frame 2280 to the end; during the replay (frames 1920–2279) they are evaluated at the replay instance's own clock (the master frame whose state it holds, divided by 60). Every schedule is written so that both clocks agree at frame 2279.

**Replay (frames 1920–2279).** At frame 1920 the picture changes to a second instance of the simulation, rebuilt from pre-roll frame 0 and advanced to the state of master frame 1320 (2.0 s before the reveal), histories included, and seen from the second view (§6.3 item 5, gate E04). The transition is designed — a cut, or a dissolve of at most 24 frames with both instances rendered and composited — and recorded in the shot list. From frame 1920 the replay instance advances at `timeScale = 0.5`, so the payoff recurs at frame 2160 (36.0 s), and at frame 2279 the instance holds the state of master frame 1500. The live instance is discarded after the transition. From frame 2280 the surviving instance continues: in P and S at `timeScale = 0.25` under the receipt; in L into the extended segment at the timeScale of its beats. `simTime` decreases exactly twice in a master: at frame 1920 and at the return.

**Return.** At the return's first frame (2580 in P and S, 5280 in L) the simulation is rebuilt to pre-roll state 0 with empty histories and held for 24 frames while a designed transition (at most 24 frames: a dissolve, a cut, a change of light) brings back the opening view; the next 96 frames (2604–2699 in P and S, 5304–5399 in L) advance through pre-roll states 1–96, one per frame, seen exactly as the opening, so the last frame equals frame 0 (gate E03).

**Base rate.** `r = 1`, `dt = 1/60`; the camera's path is a closed form in simulation time, evaluated at the fractional time. `build/timewarp.json` = `{ "r": 1, "S_star": 1536, "clamped": false, "payoff_frame": 1440 }`.

**Frame 0.** It shows the rig camera's picture at `x = 0.080 m`, already moving, with 1.6 s of history.

**Expectation (frames 480–809).** The flat print of §7.2 replaces the stack; `ghostUsed` is true on these frames; the transitions into and out of it are designed (at most 24 frames each). The readout shows the print's one speed for both panes.

**The reveal (payoff, frame 1440).** From frame 1440 the picture shows the rig from outside its axis: all seven panes in view as the flat sheets of glass they are, with the paintings on them, the space between them and the rig camera; during the payoff hold the view axis makes at least 30° with the rig's axis. The stack carries the hero accent (light caught in the glass edges, a glow on the panes — designed) from frame 1440 to the receipt; `payoffRect` = the screen-space bounding box of the seven panes. The rig keeps trucking (at a quarter speed during the hold); its own picture may appear in the reveal (a monitor, a projection, a glow on the panes) or not. How the view gets outside — a cut on frame 1440 or a move that lands on it — is designed.

**Fallback.** None required.

### 7.4 Creative brief (designed)

**The heart.** Depth is motion. A world that looks deep is seven flat paintings on glass, and the only thing that makes it deep is that the far ones slide slower than the near ones as the camera moves. The film lets the viewer fall into a painted world, then shows them the trick — and the trick is more beautiful than the illusion.

**The image that must land.** The reveal at 24 s: the view swings out of the world and the viewer sees seven flat panes of painted glass hanging in the dark, one behind the other — the world they just flew through, now plainly flat sheets, and still a single deep picture from where the rig camera stands.

**What the science requires of the picture.** The seven paintings compose one scene through the rig camera (a foreground near the lens, a far distance, layers between), each on its own pane; the parallax reads clearly (near elements crossing the frame visibly faster than far ones); the reveal shows all seven panes as flat, separated sheets, the paintings on them recognisable as the world the viewer was just in. The paintings are computed in this run — procedural brushwork, noise, simulated pigment, geometry — never an image asset and never a copy of a named film's look.

**Sparks (optional; your own are welcome).**
- A forest at dusk: branches and leaves on the nearest panes, a clearing and a lit window in the middle, hills and sky on the far panes, mist hanging between the glass.
- A sea cave: rock arches near, water and light in the middle, open sea and a low sun far away, spray drifting across the panes.
- A city in rain: railings and wet leaves near, lit windows in the middle, towers and cloud far away, the glass itself beaded with drops.

**The turn.** The reveal on the payoff: from inside the painting to outside the rig.

**The second view.** The reveal again from another place: along the edges of the panes, from below the stack, or sliding between two panes.

**L extended pictures.** Computed from the rig: two panes' slides compared for the same camera move; speed × distance equal for every pane; the lens focusing from the nearest pane to the farthest; the light balance switched off (the far panes darkening through the glass) and on again.

**Loops.** The rig camera circling, the painted world swaying in depth.

### 7.5 Correctness tests (must pass before any master is rendered)

Implement these as `tools/qa/tests.*`, runnable with one command, exit code 0 required. Each test prints its measured value; the values named as receipt checks are also written to `build/metrics.json` under `checks`.

1. **Pane distances:** `d_k = 0.5 × 1.45^k` within 1e-12 m; `d_6/d_0 = 9.2941` to four decimals.
2. **Camera path:** `x(τ)` is continuous and `dx/dτ = V(τ)` within 1e-9 m/s at 1,000 points (central differences; reference worst case 6e-10); `x = 1.755 m` at the payoff frame.
3. **Projection:** for 1,000 seeded points on each pane, the renderer's own camera matrices move the projected point by `f_px Δx / d_k` within 1e-6 px for `Δx = 0.01 m`.
4. **Measured parallax (receipt check):** the page supports `?calib=1&pane=k` (pane `k` alone, textured with seeded band-limited noise, no blur, grain, bloom or haze). Render P frames 180 and 240 of each pane this way, measure the horizontal shift between them by phase correlation (Hann window, sub-pixel refinement to 0.01 px) and require every pane's shift within 1.5 % of `f_px Δx / d_k` (with `Δx = 0.050 m`; reference for a 40° vertical field of view: 263.8 px for pane 0 and 28.4 px for pane 6). `speed_ratio_measured` = shift of pane 0 ÷ shift of pane 6, within 1.5 % of 9.2941; write it to `metrics.json` (receipt check, two decimals, no unit).
5. **Flat print:** the print's measured shift over frames 540–600 equals `f_px Δx / d_3` within 1.5 %, and the whole print moves as one (the shift measured in the left and right halves of the frame agrees within 1 %).
6. **Light balance:** with the balance on, the calibration texture's mean brightness as the rig camera sees it through the panes above is equal across panes within 2 %; with the balance off it falls as `0.92^k` within 2 %.
7. **Focus:** at five focus distances of the `how3` pull, the sharpest pane (the highest variance of the Laplacian of its calibration render) is the one nearest the focus in `1/d`, and sharpness falls monotonically with `|1/s − 1/d_k|`.
8. **Loop periodicity:** the rig camera's position at loop frame 480 equals its position at loop frame 0 within 1e-12 m.

### 7.6 Readout

Label: `Pane speed`. Value: the angular speeds of the nearest and the farthest pane across the rig camera's view (`speed_near`, `speed_far` of §7.2), one decimal each: `near 5.7°/s · far 0.6°/s`; regex `^near \d{1,2}\.\d°/s · far \d{1,2}\.\d°/s$`. In the L extended segment the label and value change as the beat sheet states: `Focus`, the focus distance in metres (`1.52 m`, regex `^\d\.\d{2} m$`); `Far pane light`, the farthest pane's light factor (`1.65×`, regex `^\d\.\d{2}×$`).

### 7.7 The naive expectation

The naive expectation is that moving a camera over a painting slides the whole picture at one speed. The expectation device is the flat print of §7.2 — the same scene as one painting at one distance — which slides as one piece; when the stack returns, the depth returns.

---

## 8. Beat sheets and captions

Captions are fixed; copy them byte for byte into `build/beats_P.json` and `build/beats_L.json` (the JSON is given in §8.5). `t0`/`t1` are seconds; frames are `round(t × 60)`. The `action` column states what the simulation does in the beat — a fact of the fixed layer. How it is shown (shots, cuts, lenses, transitions) is designed and recorded in `build/look.json`, never in the beat sheet.

### 8.1 Portrait and square masters (P, S) — 45.000 s

| id | t0 | t1 | frames | style | caption (exact) | what the simulation does | readout | rate |
|---|---|---|---|---|---|---|---|---|
| open | 0.0 | 2.0 | 0–119 | caption | `One painting.⏎Seven panes of glass.` | The rig camera trucks at 0.05 m/s across the stack (x = 0.080 m at frame 0); the seven panes slide at speeds inversely proportional to their distance; no readout | off | 1.0 |
| ruleIntro | 2.0 | 3.0 | 120–179 | caption | `The rule:` | Readout appears (near 5.7°/s · far 0.6°/s) | on | 1.0 |
| rule | 3.0 | 8.0 | 180–479 | rule | `The farther the pane,⏎the slower it slides.` | Trucking at 0.05 m/s | on | 1.0 |
| expect | 8.0 | 13.5 | 480–809 | caption | `Expected: one flat⏎picture, sliding.` | Frames 480–809: the flat print (the expectation device, ghostUsed = true) slides at the one speed of d_3 (readout: near 1.9°/s · far 1.9°/s) | on | 1.0 |
| run | 13.5 | 21.5 | 810–1289 | caption | `Near panes race.⏎Far panes crawl.` | The stack returns; the camera speed eases 0.05 → 0.10 m/s over 13.5–15.5 s (readout: near 11.5°/s · far 1.2°/s) | on | 1.0 |
| run2 | 21.5 | 24.0 | 1290–1439 | none | — | Trucking at 0.10 m/s | on | 1.0 |
| payoff | 24.0 | 31.5 | 1440–1889 | caption | `Seven flat panes.⏎Depth from distance.` | Frame 1440: the reveal — the view is outside the rig, at least 30° off its axis: seven flat panes in the dark, in the hero accent; the rig keeps trucking; 30-frame hold at 0.25 | on | 1.0 |
| payoff2 | 31.5 | 32.0 | 1890–1919 | none | — | No caption | on | 1.0 |
| replay | 32.0 | 38.0 | 1920–2279 | caption | `Again, closer.` | Frame 1920: the replay instance — rebuilt, and advanced to the state of master frame 1320 — takes over through a designed transition (a cut, or a dissolve of at most 24 frames), seen from the second view; timeScale 0.5; the payoff recurs at frame 2160 | on | 0.5 |
| receipt | 38.0 | 43.0 | 2280–2579 | none | — | Receipt card (§6.7) over the living scene, which continues at timeScale 0.25, darkened and softened as designed | off | 0.25 |
| return | 43.0 | 45.0 | 2580–2699 | caption | `One painting.⏎Seven panes of glass.` | Frame 2580: the simulation is rebuilt to pre-roll state 0 and held during a designed transition of at most 24 frames; frames 2604–2699 advance through pre-roll states 1–96 seen exactly as the opening; the opening caption stays fully visible to the last frame; readout hidden | off | 1.0 |

### 8.2 Landscape master (L) — 90.000 s

Beats `open` through `replay` are identical in content and timing to §8.1, restaged for the wide frame. Between the replay and the receipt sits the extended segment: five cards that explain the mechanism with pictures computed from the simulation, never drawn by hand, in the film's own world and style.

| id | t0 | t1 | frames | style | caption (exact) | what the simulation does | readout | rate |
|---|---|---|---|---|---|---|---|---|
| open | 0.0 | 2.0 | 0–119 | caption | `One painting.⏎Seven panes of glass.` | The rig camera trucks at 0.05 m/s across the stack (x = 0.080 m at frame 0); the seven panes slide at speeds inversely proportional to their distance; no readout | off | 1.0 |
| ruleIntro | 2.0 | 3.0 | 120–179 | caption | `The rule:` | Readout appears (near 5.7°/s · far 0.6°/s) | on | 1.0 |
| rule | 3.0 | 8.0 | 180–479 | rule | `The farther the pane,⏎the slower it slides.` | Trucking at 0.05 m/s | on | 1.0 |
| expect | 8.0 | 13.5 | 480–809 | caption | `Expected: one flat⏎picture, sliding.` | Frames 480–809: the flat print (the expectation device, ghostUsed = true) slides at the one speed of d_3 (readout: near 1.9°/s · far 1.9°/s) | on | 1.0 |
| run | 13.5 | 21.5 | 810–1289 | caption | `Near panes race.⏎Far panes crawl.` | The stack returns; the camera speed eases 0.05 → 0.10 m/s over 13.5–15.5 s (readout: near 11.5°/s · far 1.2°/s) | on | 1.0 |
| run2 | 21.5 | 24.0 | 1290–1439 | none | — | Trucking at 0.10 m/s | on | 1.0 |
| payoff | 24.0 | 31.5 | 1440–1889 | caption | `Seven flat panes.⏎Depth from distance.` | Frame 1440: the reveal — the view is outside the rig, at least 30° off its axis: seven flat panes in the dark, in the hero accent; the rig keeps trucking; 30-frame hold at 0.25 | on | 1.0 |
| payoff2 | 31.5 | 32.0 | 1890–1919 | none | — | No caption | on | 1.0 |
| replay | 32.0 | 38.0 | 1920–2279 | caption | `Again, closer.` | Frame 1920: the replay instance — rebuilt, and advanced to the state of master frame 1320 — takes over through a designed transition (a cut, or a dissolve of at most 24 frames), seen from the second view; timeScale 0.5; the payoff recurs at frame 2160 | on | 0.5 |
| how1 | 38.0 | 46.0 | 2280–2759 | caption | `Twice as far,⏎half as fast.` | The rig trucks at 0.10 m/s; the slides of two panes (pane 0 at 0.500 m and pane 2 at 1.051 m) over the same camera move are computed and compared; readout `Pane speed` | on | 1.0 |
| how2 | 46.0 | 54.0 | 2760–3239 | caption | `Speed times distance:⏎the same for every pane.` | Each pane's angular speed × distance, computed from the rig: equal for all seven (5.73 °·m/s at 0.10 m/s); readout `Pane speed` | on | 1.0 |
| how3 | 54.0 | 62.0 | 3240–3719 | caption | `One pane in focus.⏎The others soften.` | The rig lens focuses from pane 0 to pane 6 over 54–60 s (1/s eases from 2.000 to 0.2152 per metre), each pane blurred by the thin-lens law of §7.2; readout `Focus` | on | 1.0 |
| how4 | 62.0 | 70.0 | 3720–4199 | caption | `Lit brighter, far panes⏎shine through the glass.` | The light balance switches off over 62–63 s (each pane dims to 0.92^k; the farthest to 0.61) and on again over 66–67 s; readout `Far pane light` (1.65× → 1.00× → 1.65×) | on | 1.0 |
| how5 | 70.0 | 78.0 | 4200–4679 | caption | `Disney's multiplane camera,⏎The Old Mill (1937).` | The rig trucks; readout back to `Pane speed` | on | 1.0 |
| ext_end | 78.0 | 80.0 | 4680–4799 | none | — | No caption; the scene continues | on | 1.0 |
| receipt | 80.0 | 88.0 | 4800–5279 | none | — | Receipt card (§6.7) over the living scene, which continues at timeScale 0.25, darkened and softened as designed | off | 0.25 |
| return | 88.0 | 90.0 | 5280–5399 | caption | `One painting.⏎Seven panes of glass.` | Frame 5280: the simulation is rebuilt to pre-roll state 0 and held during a designed transition of at most 24 frames; frames 5304–5399 advance through pre-roll states 1–96 seen exactly as the opening; the opening caption stays fully visible to the last frame; readout hidden | off | 1.0 |

### 8.3 Loops (LP, LS) — 8.000 s, 480 frames

Exact-period construction: the rig camera moves once around a horizontal circle of radius 0.03 m over the 480 frames (`x = 0.03 cos(2πk/480)`, `y = 0.03 sin(2πk/480)` for loop frame `k`), so each pane's picture circles with an angular radius inversely proportional to its distance (3.4° for the nearest, 0.37° for the farthest) and frame 480 would equal frame 0. The loop shows the rig camera's picture, with the light balanced; the hero accent is not used.

Loop rules: no captions, no readout, no receipt; the loop shows the phenomenon at its most beautiful, in the film's world and grade. The construction above fixes only what makes the seam exact; the view, world, light and grade are designed, and wherever the construction leaves a rate or a starting state open, choose it so the loop shows the phenomenon in motion, never a still, and record it. The view is still or exactly periodic over the loop. Frame `480` (not rendered) would equal frame 0, so frame `479` differs from frame 0 by exactly one step. Loop audio follows §9.5.

### 8.4 Poster frames

Poster frame: one index in the window `1455–1620` (the reveal), the same for every format, at which all seven panes and the paintings on them read at 270 px and gate C02 passes; record the index in `decisions.md`. Clean variants omit the caption.

### 8.5 Beat sheet JSON (copy verbatim)

`build/beats_P.json`:

```json
[
 {
  "id": "open",
  "t0": 0.0,
  "t1": 2.0,
  "style": "caption",
  "caption": "One painting.\nSeven panes of glass.",
  "action": "The rig camera trucks at 0.05 m/s across the stack (x = 0.080 m at frame 0); the seven panes slide at speeds inversely proportional to their distance; no readout",
  "readout": false,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "ruleIntro",
  "t0": 2.0,
  "t1": 3.0,
  "style": "caption",
  "caption": "The rule:",
  "action": "Readout appears (near 5.7°/s · far 0.6°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "rule",
  "t0": 3.0,
  "t1": 8.0,
  "style": "rule",
  "caption": "The farther the pane,\nthe slower it slides.",
  "action": "Trucking at 0.05 m/s",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "expect",
  "t0": 8.0,
  "t1": 13.5,
  "style": "caption",
  "caption": "Expected: one flat\npicture, sliding.",
  "action": "Frames 480–809: the flat print (the expectation device, ghostUsed = true) slides at the one speed of d_3 (readout: near 1.9°/s · far 1.9°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "run",
  "t0": 13.5,
  "t1": 21.5,
  "style": "caption",
  "caption": "Near panes race.\nFar panes crawl.",
  "action": "The stack returns; the camera speed eases 0.05 → 0.10 m/s over 13.5–15.5 s (readout: near 11.5°/s · far 1.2°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": {
   "V_m_s": {
    "from": 0.05,
    "to": 0.1,
    "ease": "easeInOutCubic",
    "t0": 13.5,
    "t1": 15.5
   }
  }
 },
 {
  "id": "run2",
  "t0": 21.5,
  "t1": 24.0,
  "style": "none",
  "caption": null,
  "action": "Trucking at 0.10 m/s",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "payoff",
  "t0": 24.0,
  "t1": 31.5,
  "style": "caption",
  "caption": "Seven flat panes.\nDepth from distance.",
  "action": "Frame 1440: the reveal — the view is outside the rig, at least 30° off its axis: seven flat panes in the dark, in the hero accent; the rig keeps trucking; 30-frame hold at 0.25",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "payoff2",
  "t0": 31.5,
  "t1": 32.0,
  "style": "none",
  "caption": null,
  "action": "No caption",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "replay",
  "t0": 32.0,
  "t1": 38.0,
  "style": "caption",
  "caption": "Again, closer.",
  "action": "Frame 1920: the replay instance — rebuilt, and advanced to the state of master frame 1320 — takes over through a designed transition (a cut, or a dissolve of at most 24 frames), seen from the second view; timeScale 0.5; the payoff recurs at frame 2160",
  "readout": true,
  "timeScale": 0.5,
  "params": null
 },
 {
  "id": "receipt",
  "t0": 38.0,
  "t1": 43.0,
  "style": "none",
  "caption": null,
  "action": "Receipt card (§6.7) over the living scene, which continues at timeScale 0.25, darkened and softened as designed",
  "readout": false,
  "timeScale": 0.25,
  "params": null
 },
 {
  "id": "return",
  "t0": 43.0,
  "t1": 45.0,
  "style": "caption",
  "caption": "One painting.\nSeven panes of glass.",
  "action": "Frame 2580: the simulation is rebuilt to pre-roll state 0 and held during a designed transition of at most 24 frames; frames 2604–2699 advance through pre-roll states 1–96 seen exactly as the opening; the opening caption stays fully visible to the last frame; readout hidden",
  "readout": false,
  "timeScale": 1.0,
  "params": null
 }
]
```

`build/beats_L.json`:

```json
[
 {
  "id": "open",
  "t0": 0.0,
  "t1": 2.0,
  "style": "caption",
  "caption": "One painting.\nSeven panes of glass.",
  "action": "The rig camera trucks at 0.05 m/s across the stack (x = 0.080 m at frame 0); the seven panes slide at speeds inversely proportional to their distance; no readout",
  "readout": false,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "ruleIntro",
  "t0": 2.0,
  "t1": 3.0,
  "style": "caption",
  "caption": "The rule:",
  "action": "Readout appears (near 5.7°/s · far 0.6°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "rule",
  "t0": 3.0,
  "t1": 8.0,
  "style": "rule",
  "caption": "The farther the pane,\nthe slower it slides.",
  "action": "Trucking at 0.05 m/s",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "expect",
  "t0": 8.0,
  "t1": 13.5,
  "style": "caption",
  "caption": "Expected: one flat\npicture, sliding.",
  "action": "Frames 480–809: the flat print (the expectation device, ghostUsed = true) slides at the one speed of d_3 (readout: near 1.9°/s · far 1.9°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "run",
  "t0": 13.5,
  "t1": 21.5,
  "style": "caption",
  "caption": "Near panes race.\nFar panes crawl.",
  "action": "The stack returns; the camera speed eases 0.05 → 0.10 m/s over 13.5–15.5 s (readout: near 11.5°/s · far 1.2°/s)",
  "readout": true,
  "timeScale": 1.0,
  "params": {
   "V_m_s": {
    "from": 0.05,
    "to": 0.1,
    "ease": "easeInOutCubic",
    "t0": 13.5,
    "t1": 15.5
   }
  }
 },
 {
  "id": "run2",
  "t0": 21.5,
  "t1": 24.0,
  "style": "none",
  "caption": null,
  "action": "Trucking at 0.10 m/s",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "payoff",
  "t0": 24.0,
  "t1": 31.5,
  "style": "caption",
  "caption": "Seven flat panes.\nDepth from distance.",
  "action": "Frame 1440: the reveal — the view is outside the rig, at least 30° off its axis: seven flat panes in the dark, in the hero accent; the rig keeps trucking; 30-frame hold at 0.25",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "payoff2",
  "t0": 31.5,
  "t1": 32.0,
  "style": "none",
  "caption": null,
  "action": "No caption",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "replay",
  "t0": 32.0,
  "t1": 38.0,
  "style": "caption",
  "caption": "Again, closer.",
  "action": "Frame 1920: the replay instance — rebuilt, and advanced to the state of master frame 1320 — takes over through a designed transition (a cut, or a dissolve of at most 24 frames), seen from the second view; timeScale 0.5; the payoff recurs at frame 2160",
  "readout": true,
  "timeScale": 0.5,
  "params": null
 },
 {
  "id": "how1",
  "t0": 38.0,
  "t1": 46.0,
  "style": "caption",
  "caption": "Twice as far,\nhalf as fast.",
  "action": "The rig trucks at 0.10 m/s; the slides of two panes (pane 0 at 0.500 m and pane 2 at 1.051 m) over the same camera move are computed and compared; readout `Pane speed`",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "how2",
  "t0": 46.0,
  "t1": 54.0,
  "style": "caption",
  "caption": "Speed times distance:\nthe same for every pane.",
  "action": "Each pane's angular speed × distance, computed from the rig: equal for all seven (5.73 °·m/s at 0.10 m/s); readout `Pane speed`",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "how3",
  "t0": 54.0,
  "t1": 62.0,
  "style": "caption",
  "caption": "One pane in focus.\nThe others soften.",
  "action": "The rig lens focuses from pane 0 to pane 6 over 54–60 s (1/s eases from 2.000 to 0.2152 per metre), each pane blurred by the thin-lens law of §7.2; readout `Focus`",
  "readout": true,
  "timeScale": 1.0,
  "params": {
   "focus_inv_per_m": {
    "from": 2.0,
    "to": 0.2152,
    "ease": "easeInOutCubic",
    "t0": 54.0,
    "t1": 60.0
   }
  }
 },
 {
  "id": "how4",
  "t0": 62.0,
  "t1": 70.0,
  "style": "caption",
  "caption": "Lit brighter, far panes\nshine through the glass.",
  "action": "The light balance switches off over 62–63 s (each pane dims to 0.92^k; the farthest to 0.61) and on again over 66–67 s; readout `Far pane light` (1.65× → 1.00× → 1.65×)",
  "readout": true,
  "timeScale": 1.0,
  "params": {
   "light_balance": [
    {
     "from": 1,
     "to": 0,
     "ease": "linear",
     "t0": 62.0,
     "t1": 63.0
    },
    {
     "from": 0,
     "to": 1,
     "ease": "linear",
     "t0": 66.0,
     "t1": 67.0
    }
   ]
  }
 },
 {
  "id": "how5",
  "t0": 70.0,
  "t1": 78.0,
  "style": "caption",
  "caption": "Disney's multiplane camera,\nThe Old Mill (1937).",
  "action": "The rig trucks; readout back to `Pane speed`",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "ext_end",
  "t0": 78.0,
  "t1": 80.0,
  "style": "none",
  "caption": null,
  "action": "No caption; the scene continues",
  "readout": true,
  "timeScale": 1.0,
  "params": null
 },
 {
  "id": "receipt",
  "t0": 80.0,
  "t1": 88.0,
  "style": "none",
  "caption": null,
  "action": "Receipt card (§6.7) over the living scene, which continues at timeScale 0.25, darkened and softened as designed",
  "readout": false,
  "timeScale": 0.25,
  "params": null
 },
 {
  "id": "return",
  "t0": 88.0,
  "t1": 90.0,
  "style": "caption",
  "caption": "One painting.\nSeven panes of glass.",
  "action": "Frame 5280: the simulation is rebuilt to pre-roll state 0 and held during a designed transition of at most 24 frames; frames 5304–5399 advance through pre-roll states 1–96 seen exactly as the opening; the opening caption stays fully visible to the last frame; readout hidden",
  "readout": false,
  "timeScale": 1.0,
  "params": null
 }
]
```

Beat fields: `id`; `t0`, `t1` (s); `style` = `caption | rule | none`; `caption` (exact text or null); `action` (what the simulation does); `readout` (boolean); `timeScale` (simulation speed multiplier for the beat); `params` (a scheduled parameter change evaluated as a pure function of master time, or null).

---

## 9. Sound

The film must be fully understood with the sound off, and with the sound on it should feel twice as alive. Sound and picture are designed together: the music's shape follows the beat sheet, the payoff carries the film's loudest and clearest accent, and visible events are heard. All final audio is 48 kHz stereo, exactly as long as its video (P/S 45.000 s; L 90.000 s; loops 8.000 s), normalized with two-pass `loudnorm` to I = −14 LUFS, LRA = 11 and a true-peak target of −2.0 dBTP, so that the deliverable stays at or below −1.0 dBTP after AAC encoding (Appendix A.5).

### 9.1 Tier 0 — the engine that is always produced (the final mix when nothing better is available)

- Implement `audio/synth.*` with float64 mixing and a final soft clip `y = tanh(1.2 x) / tanh(1.2)`.
- Bed: a sine at `f0` and a triangle at `1.5·f0`, mixed 0.7/0.3, amplitude `0.75 + 0.25·sin(2π·0.08·t)`, one-pole low-pass at 900 Hz, −28 dBFS RMS (`f0 = 110.00 Hz`), with an octave doubling at −34 dBFS, since small speakers barely reproduce a fundamental below 120 Hz.
- Events: `build/events.json` lists `{t, kind, x, value}` from the bake; each event triggers a designed pluck (peak −20 dBFS, decay ≤ 0.5 s) at a pitch from the set `493.88 Hz, 440.00 Hz, 369.99 Hz, 329.63 Hz, 277.18 Hz, 246.94 Hz, 220.00 Hz` chosen by §9.2, panned by `x` (−1 left, +1 right). At most 12 events per integer-second bucket; when more occur, keep those whose index within the bucket is ≡ 0 mod k, k = ceil(n/12).
- Payoff swell: from 1.5 s before the payoff timecode, a filtered-noise rise (low-pass 300 → 3000 Hz, −24 dBFS; noise seeded with `20260928` through `mulberry32`) resolving on the payoff frame into a held chord on `f0` (root, major third, fifth; −18 dBFS; 2.0 s decay).

### 9.2 Event mapping for this concept (default; the timbre is designed, the timing is not)

Events: pane `k` emits `{t, kind: "pane", x: 0, value: k}` each time its angular travel across the rig camera's view (camera travel ÷ `d_k`, in degrees) crosses a multiple of 4°; its pitch is entry `k` of the set (pane 0, the nearest, the highest; pane 6, the farthest, the lowest). The near panes tick quickly and the far ones slowly, so the parallax is heard as a polyrhythm. During the flat print every pane moves at the one speed of `d_3`, so their ticks coincide: count coincident ticks as one event sounding all their pitches (a chord in unison rhythm). Reference: about 4.3 events per second at 0.05 m/s and 8.5 at 0.10 m/s; the density cap rarely applies.

### 9.3 Tier 1 — generated assets (only when §5 item 6 recorded `generated_sound_available: true`)

1. **One-shot sounds** for the event classes of §9.2 (at most six descriptions per film, each ≤ 3 s; `POST /v1/sound-generation` or the official SDK, `npm i @elevenlabs/elevenlabs-js` or `pip install elevenlabs`). The description names a material and a gesture, never a genre or a product name. Trim to the first zero crossing, 5 ms fade-in, 20 ms fade-out, resample to 48 kHz, peak-normalize to −20 dBFS, and place by the engine at exactly the bake's event times with the same density cap and pan rule. Pitch variation by resampling a one-shot, never by regenerating.
2. **A music bed**: one request for the 45.000 s bed shared by P and S, one for the 90.000 s L bed (`POST /v1/music` with a description and the exact length in milliseconds; where the endpoint supports a composition plan, give sections that follow the beat sheet: quiet 0–8 s, rising 8–24 s, a clear accent at 24.0 s, easing from 32 s, calm under the receipt, a final sustained tone). The description names mood, tempo, instrumentation and dynamics in plain words; no artist names, no titles. Level-set to −30 dBFS RMS before events and narration; fade in over 0.5 s and out over 1.0 s ending on the last frame; if the delivered length differs by more than 0.5 s, trim from the end with a 1.0 s fade; never time-stretch. Visual accents may be timed to the bed's beats inside the fixed timecodes.
3. **Narration** (optional, a design decision): one clip per captioned beat reading exactly that beat's caption (line breaks as a short pause), in order, plus receipt rows 2 and 4; nothing else is ever spoken. Model `eleven_multilingual_v2` (or, if `GET /v1/models` does not list it, the first listed text-to-speech model; record it); one voice for the film (list `GET /v1/voices`; eligible: `premade`, not a character or celebrity, not derived from a named person; choose by listening proxies — speaking rate near 2.6 words per second, low crest factor — and by the film's tone; record the choice). Each clip starts at `t0 + 0.15 s` of its beat and ends by `t1 − 0.30 s`; the receipt clips: row 2 at receipt `t0 + 0.15 s`, row 4 starting 0.5 s after row 2 ends, the later one omitted if it cannot end by `t1 − 0.30 s`. Narration at −20 dBFS RMS; bed and events ducked by 6 dB with 100 ms ramps while a clip plays. The engine writes two stems beside every final mix, `audio/<F>_stem_music.wav` and `audio/<F>_stem_voice.wav`. Never narration in loops.

Every request and response is recorded in `audio/generated/manifest.json` (endpoint, description or `caption_text` and `request_text`, model and voice identifiers, parameters, timestamp, sha256 of the returned file). The key is read from the file of §5 item 6 at call time and never written anywhere. Budget: at most 6 sound descriptions, 2 music requests (plus one retry each) and the narration clips; a failed request is retried once, then the Tier 0 element takes its place and the fallback is recorded.

### 9.4 Designing the sound

Render two complete alternatives of the P mix that differ in kind (a third only if the time plan has room) (for example: Tier 0 alone; generated one-shots over the Tier 0 bed; the generated music bed with generated one-shots; any of these with narration; or three Tier 0 variants if the generated tier is unavailable). Measure each (onset alignment with `events.json`, the payoff accent, RMS per beat, clicks and level jumps, channel balance, spectral variation over time, narration intelligibility and overlap), listen through those measurements, and choose the design that best serves the moment of §10.5 and the rubric: every visible event class audible, the payoff the loudest and clearest moment, nothing drawing attention to itself when the picture is calm, nothing that sounds like a default preset. Record the alternatives, the measurements and the reason in `decisions.md`. The L mix uses the chosen design with its own 90 s bed and clips.

### 9.5 Sync and loops

Events and narration are placed by the bake's frame-indexed times, so synchronization holds by construction; gate A03 checks the lengths, G01 the payoff accent, G05 the narration timing. Loops carry the Tier 0 bed only (unless §9 states a concept rule), made exactly periodic: every oscillator frequency rounded to an integer multiple of `1/8.000` Hz and `fLFO = 1/8.000` Hz; no noise, no events, no generated assets. The synth renders N + 512 samples; samples `[N, N+512)` equal samples `[0, 512)` within 1e-3 full scale (gate F02).

---

## 10. How this studio works (method)

The method serves one goal: the best film this studio can make within a fixed amount of time. Ideas are judged while they are cheap — as a written plan, as still frames, as short clips — and the full masters are rendered once, at the end, when nothing about the look is still open. Generation and critique are separate steps; reviewers see the evidence, never your summary.

### 10.1 Time: the budget and the living plan

- **Budget.** The whole production, from §5 to §14.6, has 4 to 8 hours of wall-clock time on this machine. Aim to finish in about 5 to 6 hours. **Eight hours after `started_utc` is a hard limit.**
- **The plan.** In Stage 0, write `plan.md`: one row per stage of this section with its planned minutes, the planned UTC time at which it ends, and the projected finish of the whole run. Start from the reference durations of §15 and adjust them to this film (a heavier world, a slower render, a simpler simulation).
- **Adapt it at every stage.** At the end of every stage, append to `plan.md` the actual UTC time (`date -u`), the elapsed time since `started_utc` and a re-projected finish, and re-plan the stages that remain. When the projection passes 7 hours, cut scope by the ladder of §10.12, one rung at a time, until it fits; record every cut and its reason. When a stage finishes early, give the saved time to whatever will improve the film most — usually look development.
- **Deadlines.** The final render (Stage 6) starts no later than 5 h 15 min after `started_utc` — earlier if the plan says so — with whatever look is locked at that moment. At 8 hours, stop improving: let a running render finish, then complete the mux, the checks and the records with what exists, and list everything unfinished in `open-items.md`.
- **Never idle, never unattended.** Long jobs (renders) may run as separate processes; while one runs, check it regularly and use the time for work that does not compete for the GPU (sound, records, review evidence). Never end a stage, or the production, while a job you started is still running.

### 10.2 Stage 0 — Pre-flight, reading and the plan (gate: `run.json` and `plan.md` exist)
Do §5. Read this brief fully once before writing code. Read `reference/INDEX.md`, the concept's entry in `reference/concepts/`, and skim `reference/craft/` for techniques that could serve this film. Write `plan.md` (§10.1). Start `decisions.md` with the header and the first entry: the deviations and interpretations you already anticipate.

### 10.3 Stage 1 — Simulation, bake and tests (gate: tests pass)
1. Implement the simulation of §7.2–7.3 as a pure module (no DOM, no globals, `PARAMS` exported), seeded by Appendix A.1.
2. Implement the bake: it replays every format's full schedule (P, L, S, LP, LS, including holds, the replay rewind, the receipt and the return) and writes `build/metrics.json` as `{P: [...], L: [...], S: [...], LP: [...], LS: [...], checks: {...}}` — one entry per frame with the metrics of §7.6 — and `build/events.json` (§9.2). If you choose bake-and-replay (§6.1), it also writes the per-frame state the renderer reads (binary, under `build/state/`). Apply the time mapping and fallbacks of §7.3 and record what happened.
3. Implement and run the tests of §7.5. Do not proceed until they pass. If a test cannot pass without changing a fixed parameter, follow §14.5.

### 10.4 Stage 2 — Beat-sheet lock (gate: checksums match)
Write `build/beats_P.json` and `build/beats_L.json` from §8.5: the text inside the fenced block followed by exactly one newline. `sha256sum` must give `79ea149cac1e84f4d814cf6a59a3b9635dfe93de6d49a24b024c809d96e18904` and `aa68f5a09639e9e7c6540977d306b02dec9fd90e5b9784adca063f9aa58b16f2`. If a checksum differs, the copy is wrong, not the brief.

### 10.5 Stage 3 — The treatment and review 1 (gate: `reviews/review_1_notes.md` written)
1. **The moment.** Write in `decisions.md` one line beginning `The moment:` — the single image of this film a first-time viewer would describe afterwards: what they see and when (inside the payoff or replay beats). Every later decision is judged by whether it makes that image more beautiful, clearer or more surprising.
2. **The treatment.** Write `lookdev/treatment.md` (one or two pages): two or three genuinely different directions for the whole film — different worlds, styles or kinds of light (§7.4's sparks or your own) — each in a paragraph; then, for the direction you favour: the world and its story, palette and hero accent, light, materials, lens language, the shot list per beat for P and how L and S differ, the turn, how the payoff is staged as the film's spectacle, the sound idea, and the entries of `reference/craft/` that informed it. A quick sketch frame per direction is welcome and optional.
3. **Review 1 — the plan** (§13): the art panel reviews the treatment. Write `reviews/review_1_notes.md`, choose the direction (or a hybrid), and fold the accepted changes into the treatment before anything is built.

### 10.6 Stage 4 — Look development and review 2 (gate: the look is locked)
1. Build the chosen direction and render its hero frames at full quality in P — frame 0, the rule beat (frame 300), the payoff (frame 1470), the replay (frame 2190, just after the payoff recurs) and the receipt (frame 2400) — into `lookdev/iter_N/`.
2. **Iterate.** Critique each frame against the rubric of §6.10 in `lookdev/iter_N/critique.md` (what is default, flat, muddy, dead or over-done; what is beautiful), make the three changes that raise the lowest scores most, and render again. Run the fast checks on every iteration's frames — text size and contrast at 270 px, text inside the safe areas, the payoff element inside the frame's central region (checks D03–D05 and C02, applied to stills) — so that the final run finds nothing new. Continue while an iteration raises a hero frame by a point, until every hero frame scores 8.5 or above on every line or the time box of `plan.md` ends.
3. **Restage L and S** with their own shot lists; render their opening and payoff frames and bring them to the same look.
4. **Review 2 — the look** (§13): the art panel reviews the frames. Write `reviews/review_2_notes.md`, make the accepted changes, and render the affected hero frames once more.
5. **Lock the look.** Write `lookdev/selected.md` (the look in words, the final scores, what the iterations taught) and `build/look.json` (every designed value the renderer reads). Decide the Tier 0 timbre of §9.2 here as well.

### 10.7 Stage 5 — Motion: animatic, key clips and review 3 (gate: `reviews/review_3_notes.md` written and its accepted changes made)
1. **Animatic.** Every format at quarter resolution and 15 fps (`build/animatic_<F>.mp4`) with a draft sound mix, and contact sheets (Appendix A.6). Confirm: the opening caption on frame 0; `The rule:` at 2.000 s; the payoff on frame 1440; the receipt on time; the last frame matching the first; the turn where the treatment puts it; every cut at least 1.5 s from the next.
2. **Key clips.** Partial renders at full specification of the moments that decide the film, in P: the opening (0–4 s), the turn (2 s either side of it), the payoff (22.5–27.5 s) and the replay's payoff (2 s either side of frame 2160); in L and S, the payoff only. A clip that starts mid-film rebuilds its histories first (§11.3). Run the fast checks on the clips (flash, nothing dead, caption timing: C01, C03, D02).
3. **Review 3 — the motion** (§13): the art panel reviews the animatic, the clips and the draft sound. Write `reviews/review_3_notes.md`, make the accepted changes, re-render only the clips they touch to confirm them, and update `build/look.json`.

### 10.8 Stage 6 — The final render (gate: exact frame counts, every identity verified)
Render P, L, S, LP and LS once, at full specification, with at most two pages at a time (§11.4). Verify the frame counts with ffprobe and the identity file of every segment (§11.3). While it renders, prepare the sound (Stage 7) and the evidence for the final look.

### 10.9 Stage 7 — Sound and mux (gate: loudness in spec)
Produce the mixes of §9 for every duration; two-pass loudnorm; mux (Appendix A.4–A.5).

### 10.10 Stage 8 — Automated checks (gate: `qa/qa_report.md` with no unexplained failure)
Run the checks of §12. One fix pass at most: fix the cause, re-render only the segments a defect touches (never the whole set for a local defect) and re-run the affected checks. Whatever remains goes to `open-items.md` with its measured value.

### 10.11 Stage 9 — Final look and finalization (gate: §14 complete)
The art producer's final look (§13.4); fix only the defects it names, by segment, if the plan allows; then the manifest, README, postmortem, open items and the final directory check (§14).

### 10.12 The scope ladder
When `plan.md` projects a finish beyond 7 hours, cut in this order, one rung at a time, and record each cut: (1) look iterations beyond the current one; (2) sketches of the alternative directions; (3) sound alternatives (keep one design); (4) the generated sound tier (Tier 0 becomes the mix); (5) the key clips of L and S (P's clips stay); (6) the depth of the L and S restaging (the same look with simpler shot lists); (7) the fix pass of Stage 8 (failures become open items). Never cut: the correctness tests, the fixed layer (captions, timecodes, numbers), the five videos and six posters, legibility and flash safety, the three reviews (they may be shorter, never skipped) and the records.

### 10.13 Separation of duties
One studio plays every role, so separation is enforced by sequence and evidence: the builder never grades their own work from memory. Run every review of §13 as a separate step: open only that review's evidence and the reviewer's brief, write the review in one sitting, and do not open `decisions.md` or earlier reviews until it is saved.

---

## 11. Engineering notes (traps already found on this machine)

### 11.1 Interfaces
- The simulation module exports `PARAMS` and `createSim(seed)` with `step()`, `state()`, `metrics()`, `events()`; pure; fixed `dt`.
- The page (or the overlay page over plates) exposes `window.renderFrame(i, {draw})` (advances to `i`, updates every history in order — trails and ribbons are state — renders unless `draw === false`, updates the text), `window.probe()` (§12.0), `window.__renderer` (the WebGL renderer string) and `window.__ready`; it honours `?notext=1` (hides every text node and its backing) and `?glyphs=0` (hides glyphs, keeps backings); `renderFrame(i)` with `i` below the current frame rebuilds from pre-roll frame 0.
- Every render process logs its full encoder command line, every console message, every page error, every request URL, the renderer string, the identity check and one timing line per frame.

### 11.2 Determinism across engines
Node and Chromium disagree in the last bits of the transcendental `Math` functions. For a chaotic simulation, either bake the state and let the renderer only read it, or implement the simulation with IEEE-exact operations and a portable implementation (for example an fdlibm port or a fixed-term series) of every transcendental function it uses, and verify bit equality between the two engines on 200,000 inputs. Rendering-side uses of `Math.sin` (camera paths, shader parameters) are harmless.

### 11.3 Capture and encode
- `page.screenshot` at 2× costs 3–5 s per frame once grain or dither makes the PNG incompressible. The DevTools capture `Page.captureScreenshot` with `optimizeForSpeed: true` costs about 0.5 s, **but at device scale 2 it returns CSS-pixel resolution unless `clip.scale` equals the device scale** — silently discarding the supersampling. With `clip.scale` set to the device scale it is pixel-identical to `page.screenshot` (verified on this machine).
- Under load the fast capture has returned **stale frames** (an earlier frame captured after `renderFrame` returned). Every captured frame must carry an identity: the page draws the frame index into an 8-pixel strip below the picture (16 cells, most significant bit first) in the same task that renders the frame; the encoder crops the strip off and writes it to a side file; the driver decodes every frame's index after the segment and re-renders any segment with a mismatch (Appendix A.3, verified on this machine).
- A segment that starts at frame `s > 0` first runs `renderFrame(k, {draw: false})` for every `k < s` so histories match the sequential render; the identity check (gate B01) and the determinism check (gate B02) cover the joins.

### 11.4 GPU and machine discipline
- This laptop's integrated GPU has lost its Vulkan device under heavy parallel load (eight render pages, or two productions at once), producing white frames and finally a machine crash. Never run more than two rendering pages at once, never run heavy QA renders in parallel with a master render, and never start a render while another production renders on this machine.
- Detect context loss (console messages naming `CONTEXT_LOST` or `DEVICE_LOST`, or a `webglcontextlost` event) and stop the process with a non-zero exit; re-render that segment from its first frame (up to three attempts, each recorded).
- Check `free -g` before each render group; if less than 8 GB is available, wait.

### 11.5 Loudness through AAC
AAC encoding raises the true peak by 0.3–0.7 dB. Normalize to −2.0 dBTP so the delivered file measures at or below −1.0 dBTP (gate A04).

### 11.6 Records
Every heading in `decisions.md` carries the UTC time read from `date -u`, never an estimate. Every fallback, deviation and interpretation is recorded when it happens.

---

## 12. Automated checks (every check is mandatory)

These checks protect delivery, truth, safety and legibility; they never judge taste — taste is the art panel's job (§13). Write one script, `tools/qa/gates.*`, that runs them all in under 30 minutes and writes `qa/qa_report.md` with one row per check: id, check, measured value, threshold, PASS/FAIL, evidence path. Never write or edit the report by hand and never relax a threshold. A FAIL that cannot be fixed within the time plan stays a FAIL, with its explanation in `decisions.md` and a row in `open-items.md`. The cheap checks (C01–C03, D02–D05) also run during Stages 4 and 5 on stills and clips (§10.6, §10.7), so the final run finds nothing new.

### 12.0 Inputs

1. **Probe.** For every format, run `renderFrame(i)` for every frame without capture and append one JSON line per frame from `window.probe()` to `qa/probe_<F>.jsonl`. `probe()` returns `{frame, t, beatId, simTime, timeScale, shotId, camera, fontLoaded, fontFamily, fontSizes, captionVisible, captionText, captionRect, readoutVisible, readoutText, readoutRect, receiptVisible, receiptLines, receiptRect, labelRects, payoffRect, ghostUsed, metrics}`. Rects are CSS px `{x, y, w, h}` or `null`; `captionVisible` is caption opacity ≥ 0.999; `camera` is `{pos, target, fov}` or `null`; `labelRects` lists every other visible text node; `payoffRect` is the screen-space bounding box of the payoff element of §7.3; `fontSizes` is `{caption, rule, readoutLabel, readoutValue, receipt: [6]}` from computed style.
2. **Captures.** PNG captures of P frames 0, 1440 and 2699 in two fresh browser sessions (B02); the last frame and frame 0 of every master; loop frames 0, 1 and N−1; `?glyphs=0` captures at every caption's midpoint, at 12.0 s and at the receipt's midpoint.
3. **Decoded deliverables.** A 2 fps set and a 10 fps set at 270 px wide.
4. **Audio.** `loudnorm` JSON for every deliverable; WAV statistics (sample count, peak, DC, RMS per window, the largest jump between consecutive samples, the loop's extension samples).

### 12.1 A — Delivery (all five videos unless stated)

| id | check | method | threshold |
|---|---|---|---|
| A01 | Container | `ffprobe` stream and format fields; MP4 box order | `h264` High, `yuv420p`, exact dimensions of §6.2, `60/1` fps, `bt709` primaries, matrix and transfer, `tv` range; `moov` before `mdat` |
| A02 | Frames and duration | `-count_frames`; stream duration | exactly 2700 / 5400 / 480 frames; duration = frames / 60 ± 0.001 s |
| A03 | Audio stream and length | `ffprobe`; WAV sample count | one AAC stream, 48 kHz, 2 channels, ≥ 160 kb/s; samples = frames × 800; audio and video durations within 1024 samples |
| A04 | Loudness | `loudnorm print_format=json` on each deliverable | −15.0 ≤ I ≤ −13.0 LUFS; true peak ≤ −1.0 dBTP |
| A05 | No duplicated frames | `ffmpeg -f framemd5` | no two consecutive identical frames outside the 24 held frames at the start of the return |

### 12.2 B — Integrity

| id | check | method | threshold |
|---|---|---|---|
| B01 | Frame identity | identity files of every delivered segment (§11.3) | every captured frame carries its own index; 0 mismatches |
| B02 | Determinism | P frames 0, 1440, 2699 captured in two fresh sessions | mean abs diff ≤ 0.5/255 for each pair |
| B03 | What is seen is what was baked | probe `metrics` at frames 0, 1440, 2279 (L also 3600) vs `build/metrics.json` | equal to relative 1e-9 |
| B04 | Clean final render | render logs of the delivered segments | 0 page errors, 0 context losses, one renderer string throughout |

### 12.3 C — Picture safety

| id | check | method | threshold |
|---|---|---|---|
| C01 | Flash safety | 10 fps set at 270 px: mean luma per sample | at most 3 changes > 20/255 in any 1.0 s window; no single change > 40/255 except on a cut declared in `look.json` |
| C02 | Payoff in view | probe `payoffRect` on frames 1440–1469 and on the poster frame | at least 80 % of its area inside the frame minus a 10 % margin on every side |
| C03 | Never dead | 2 fps set: mean abs diff of consecutive samples | no 2 s run (4 pairs) below 0.1/255, outside the held frames of the return |

### 12.4 D — Text

| id | check | method | threshold |
|---|---|---|---|
| D01 | Captions exact | `sha256sum build/beats_*.json` (§10.4); probe `captionText` at each beat's midpoint | checksums match; the rendered text equals the beat's caption, line breaks included (no automatic wrapping) |
| D02 | Caption timing | probe `captionVisible`, `captionText` | each caption fully visible from `t0 + 0.4 s` to `t1 − 0.25 s`; never two captions fully visible on one frame; the opening caption fully visible on frame 0 and on the last frame |
| D03 | Type sizes | probe `fontFamily`, `fontSizes` | Archivo (or the recorded fallback); every size within ±12 % of §6.4's reference; at quarter scale, captions ≥ 16 px and the readout value ≥ 9.5 px |
| D04 | Contrast | `?glyphs=0` captures of §12.0 | contrast of the text colour against the mean colour behind each text rectangle ≥ 4.5:1; at most 1 % of the pixels in the rectangle inflated by 12 px at luma ≥ 250 |
| D05 | Safe areas | probe rects | every visible text rectangle inside §6.4's text-safe area |
| D06 | Readout | probe `readoutVisible`, `readoutText` | visible from frame 120 until the receipt starts; every value matches §7.6's format; at least 20 distinct values |
| D07 | Receipt | probe `receiptLines` at the receipt's midpoint | the six rows of §6.7; row 4 equals the `metrics.json` value formatted as §7.5 states |
| D08 | Words and glyphs | all on-screen strings and `README.md` | none of `share, follow, subscribe, comment, wait for it, you won't believe, insane, crazy, mind-blowing, epic, ultimate, hack, secret`; no `!`; no imperative to the viewer; every glyph in Archivo; words of three or more capitals only as listed: none |

### 12.5 E — Structure

| id | check | method | threshold |
|---|---|---|---|
| E01 | Payoff on time | probe `metrics`, `timeScale` | the payoff state change of §7.3 is first shown on frame 1440; `timeScale` equals the hold speed on frames 1440–1469 |
| E02 | The rule on time | probe | `The rule:` fully visible on frame 150; the rule line on frame 240 |
| E03 | Return | captures of the last frame and frame 0 of P, S and L | mean abs diff ≤ 1.5/255 |
| E04 | Replay | probe `simTime`, `camera` | `simTime` decreases exactly twice (frame 1920 and the return's first frame); the payoff recurs on the frame stated in §7.3; the view there differs from the view on frame 1440 (camera position by ≥ 25 % of the camera–target distance, or the lens by ≥ 10°, or a declared different view) |
| E05 | Cuts | probe `shotId` vs the shot list in `look.json` | every cut declared; cuts ≥ 1.5 s apart; no shot change between two frames of 1440–1469 (a cut landing on frame 1440 is allowed) |

### 12.6 F — Loops

| id | check | method | threshold |
|---|---|---|---|
| F01 | Seam | captures of loop frames N−1, 0 and 1: `d_seam` = diff(N−1, 0), `d_step` = diff(0, 1) | `0.5 × d_step ≤ d_seam ≤ 1.5 × d_step + 0.2/255` |
| F02 | Periodic sound | samples `[N, N+512)` of the extended render vs `[0, 512)` | equal within 1e-3 full scale |

### 12.7 G — Sound

| id | check | method | threshold |
|---|---|---|---|
| G01 | Payoff accent | RMS of the 0.5 s from the payoff vs the RMS of the 3.0 s ending 0.5 s before it (P and L) | at least +3 dB |
| G02 | Clean signal | normalized WAVs | largest jump between consecutive samples ≤ 0.25 full scale; abs(mean) < 0.001 per channel; no sample at ±32767 |
| G03 | Never silent | RMS per 3.0 s window; RMS of the first 0.5 s | every window above −60 dBFS; the first 0.5 s above −45 dBFS |
| G04 | Generated assets | `audio/generated/manifest.json`; `grep` of `RUN` | every generated file listed with endpoint, text, parameters and sha256; the key's first 8 characters appear nowhere in `RUN`; `n/a` when the tier is unused |
| G05 | Narration | clip texts and placements | every clip reads a caption or receipt row 2 or 4 exactly; starts at `t0 + 0.15 s`; ends by `t1 − 0.30 s`; no overlaps; `n/a` without narration |

### 12.8 H — Science

| id | check | method | threshold |
|---|---|---|---|
| H01 | Tests | the tests of §7.5 | exit 0 |
| H02 | Parameters | canonical JSON of the exported `PARAMS` vs §7.2 | identical after key sorting |
| H03 | Receipt check | `metrics.json.checks[speed_ratio_measured]` | within the threshold of §7.5 |
| H04 | Numbers traced | every numeral in `readoutText` and `receiptLines` | each one comes from `metrics.json`, `PARAMS` or a fixed string of this brief |

### 12.9 L — Records

| id | check | method | threshold |
|---|---|---|---|
| L01 | Deliverables | the rows of §3; `sha256sum deliverables/*` vs `manifest.json` | all present and matching |
| L02 | Time plan | `plan.md` | planned and actual times (from `date -u`) for every stage, the re-projections and every scope cut; total elapsed ≤ 8 h, or the overrun explained |
| L03 | Reviews | `reviews/` | reviews 1–3 with all four reviewers and the final look; every change has a disposition in the notes |
| L04 | Records | `decisions.md`, `README.md`, `postmortem.md`, `open-items.md` | headings carry `date -u` times; README and postmortem as §14; every failed check listed in `open-items.md` |

### 12.10 Implementation notes
- **MP4 box order (A01):** read 8-byte headers `(uint32 size, 4-char type)` from offset 0, advancing by `size` (1 = a 64-bit size follows; 0 = to the end of the file).
- **Flash (C01):** decode at `fps=10,scale=270:-1`; mean luma `0.2126R + 0.7152G + 0.0722B`; a change is abs(Δ) > 20; count within each sliding window of 10 samples.
- **Contrast (D04):** relative luminance of the mean colour behind the text and of the text colour; ratio `(L1 + 0.05)/(L2 + 0.05)`.

---

## 13. The art panel (three reviews and a final look)

Reviews happen where changes are cheap: on the plan, on still frames and on short clips — never on a finished master that would have to be rendered again. Every review is done by the same panel of four art producers. Each reviewer writes from the stated perspective, as a separate step that sees only that review's evidence (§10.13). Technical correctness is not the panel's job: the tests and the automated checks cover it.

### 13.1 The panel
- **The art producer** — the creative lead of a leading motion-design studio, deciding whether this film goes on the studio's showreel. Judges the moment, wonder, the arc as a first-time viewer would feel it, coherence and ambition; scores rubric lines 1, 7, 9 and 10; names the single biggest problem and one bold idea that would change the film's most important image.
- **The cinematographer** — a director of photography known for light. Judges light, depth and air, material, composition, lens and camera; scores rubric lines 2–6.
- **The motion designer and editor** — a title-sequence designer who also cuts. Judges timing, pacing, transitions and cuts, the turn, the typography's placement, backing and legibility, the readout and the receipt; scores rubric lines 6–8.
- **The sound designer** — a film sound designer. Judges whether the sound makes the film twice as alive: the shape of the music, the payoff accent, timbres, silence and the mix; in review 2 it judges the sound plan and the timbre chosen for the look.

Each review is at most one page: **Scores** (the reviewer's rubric lines, a sentence each; in review 1 the score is for what the plan promises), **What works** (one or two sentences), **Changes** (exactly three, ranked by impact: what to change, where in the film, which rubric line it raises, and why it serves the moment — concrete enough to implement without a conversation, never touching the fixed layer) and **Verdict** (yes or no, one sentence). The art producer adds **The biggest problem** and **The bold idea**.

### 13.2 Evidence per review (in `reviews/review_N/evidence/`, built fresh for each review)
- **Review 1 — the plan:** `lookdev/treatment.md`, §7 of this brief, the beat sheets, any sketch frames.
- **Review 2 — the look:** the latest hero frames at full size and at 270 px wide, the L and S opening and payoff frames, the revised treatment, the self-critique scores and the Tier 0 timbre choice.
- **Review 3 — the motion:** the animatic and its contact sheets, the key clips as files and as frame strips (every 4th frame), the draft mix's waveform and spectrogram images and `build/events.json`, the treatment.
- **The final look:** the posters, the contact sheets of the finished masters, P frames at 0, 2.5, 8, 24.5, 36 and 42 s, and the check summary.

### 13.3 Notes and changes
After each review, write `reviews/review_N_notes.md`: the four reviews' changes merged, conflicts resolved with a reason, each change with a disposition — **done**, **partly** (what and why) or **not done** (only when the fixed layer forbids it or the time plan has no room, said plainly). The art producer's first change and the cinematographer's first change are always done unless the fixed layer forbids them. Add the panel's scores to the stage's row in `plan.md`, so quality and time are tracked together.

### 13.4 The final look
After the automated checks, the art producer looks at the finished film's evidence (§13.2) and writes `reviews/final_look.md`: scores on all ten rubric lines, the defects that must be fixed now — a broken frame, unreadable text, a sound fault; never a redesign — and a one-sentence verdict. A defect is fixed by re-rendering only the segment it touches, once, if the time plan allows; otherwise it becomes an open item.

---

## 14. Finalization

### 14.1 `deliverables/manifest.json` schema

```json
{
  "brief": "multiplane-camera", "brief_version": "3.1", "title": "The Multiplane Camera",
  "run_dir": "<RUN>", "started_utc": "<ISO>", "finished_utc": "<ISO>", "elapsed_h": 0.0,
  "seed": 20260928,
  "tools": {"node": "", "python": "", "browser": "", "renderer_stack": "", "ffmpeg": "", "font": "Archivo|DejaVu Sans", "gpu_renderer": ""},
  "deliverables": [{"file": "", "sha256": "", "bytes": 0, "width": 0, "height": 0, "frames": 0, "duration_s": 0.0,
                    "loudness_out": {"I": 0, "TP": 0, "LRA": 0}}],
  "checks": {"speed_ratio_measured": 0.0},
  "time_warp": {},
  "time": {"stages": [{"stage": "", "planned_min": 0, "actual_min": 0}], "scope_cuts": []},
  "look": {"look_sha256": "", "iterations": 0, "final_scores": {"frame0": [], "rule": [], "payoff": [], "replay": [], "receipt": []}, "turn": {"t0": 0, "t1": 0, "kind": ""}, "hero_accent": ""},
  "sound": {"design": "", "generated_tier_available": false, "narration": false, "voice_id": "", "tts_model": ""},
  "gates": {"passed": 0, "failed_with_explanation": 0},
  "reviews": [{"review": "plan|look|motion|final", "art_producer": {"verdict": ""}, "cinematographer": {"verdict": ""}, "motion_editor": {"verdict": ""}, "sound_designer": {"verdict": ""}, "changes_done": 0, "changes_total": 0}],
  "open_items": 0
}
```

### 14.2 `deliverables/README.md`

Sections, in order: what the film shows (three sentences, no adjectives of praise); the rule as stated on screen; the world in one paragraph (from `lookdev/selected.md`); the deliverable table with durations and checksums; the measured check value with its threshold; the sources of §7.1; how to reproduce; the check summary; the panel's verdicts per review and the final scores; the time (planned and actual per stage, the scope cuts); the open items, if any.

### 14.3 `postmortem.md`

Five things that went right and five that went wrong, each about the process, each one sentence with the stage number of §10. Then the timing table from `plan.md` (stage, planned, actual). Then one paragraph: the single root cause behind most of the wrongs, if there is one.

### 14.4 Final directory check

`find RUN -type f | sort`: every row of §3 exists; delete nothing; `sha256sum deliverables/*` matches `manifest.json`.

### 14.5 Escalation and BLOCKED protocol

Stop the run only when a prerequisite of §5 cannot be met after its fallback, when a test of §7.5 cannot pass without changing a fixed parameter, or when the base directory is not writable. Then write `RUN/BLOCKED.md` (or `<OUTPUT>/multiplane-camera/BLOCKED-<timestamp>.md` if `RUN` could not be created) with what was attempted, the exact error text, what would be needed, and everything completed.

### 14.6 Done

The run is done when §3 is complete, `qa/qa_report.md` shows every check PASS or failed-with-explanation, the final look is written, `manifest.json` validates and `postmortem.md` exists — or when the 8-hour limit of §10.1 was reached and the delivery was completed with what existed (every deliverable present, everything unfinished in `open-items.md`). Write the deliverable table, the check value, the elapsed time, the panel's final verdict and the open-items count as the last section of `deliverables/README.md`, and print the same lines as the last output of the run.

---

## 15. What to expect

Reference durations on this machine (a laptop with an integrated GPU); use them for the first version of `plan.md` and record your actual times there:

| stage | reference |
|---|---|
| 0 Pre-flight, reading, the plan | 15 min |
| 1 Simulation, bake and tests | 20–45 min |
| 2 Beat-sheet lock | 2 min |
| 3 Treatment and review 1 | 20–30 min |
| 4 Look development and review 2 | 60–120 min |
| 5 Animatic, key clips and review 3 | 40–60 min |
| 6 Final render (five videos at 2×, two pages) | 60–70 min |
| 7 Sound and mux (mostly while Stage 6 renders) | 20–30 min |
| 8 Automated checks and one fix pass | 20–45 min |
| 9 Final look and finalization | 15–20 min |
| total | about 5 to 6.5 hours; 8 hours is the hard limit |

Measured costs: one frame at 2× takes about 0.6–0.7 s with two pages rendering, so the five videos (11,520 frames) take about an hour; a frame at 1× is about 2.5 times faster; a 4 s clip at full specification takes 2–3 minutes; a quarter-resolution animatic of P takes about 5 minutes.

What good looks like: the tests pass with margin in Stage 1; the panel's verdict on the plan is yes, or yes with changes; the look reaches 8 or more within three to five iterations; the clips need one round of changes; the final render starts on time; the checks pass on their first run except for one or two defects fixed in the single pass.

Known pitfalls (check each): starting the final render late; rendering the full masters to fix a local defect; polishing look development past its time box; reviewing a finished master instead of stills and clips; waiting idle on a render, or ending a stage while one still runs; ES modules blocked from `file://` (serve over loopback); the GPU flags missing so the software renderer runs; tone mapping applied twice; textures and colours in the wrong colour space; instance matrices not flagged for update; shadow acne on coplanar surfaces; bloom bleeding into text; depth of field blurring the region behind the readout; grain visible at 270 px; a `renderFrame` that steps without updating histories; fonts not loaded on the first frames; unseeded shader noise; the fast capture at CSS-pixel resolution; stale captured frames; GPU device loss under parallel load; a loop whose last frame equals the first; ffmpeg back-pressure (await each write); frame sequences written to disk by mistake; concat duplicating a frame at a join; loudnorm applied once instead of two-pass; the true peak rising in AAC; audio a few milliseconds longer than the video.

Concept-specific pitfalls:

- Moving the panes instead of the camera with equal on-screen speeds (a flat picture); the parallax must come from the geometry: one camera move, seven distances.
- Painting the far panes at the same scale as the near ones: a pane at 4.6 m fills the view with a region nine times wider than one at 0.5 m, and must be painted for it.
- Glass that is only transparent: each pane attenuates by 0.92, and the light balance of §7.2 must be modelled, not faked by brightening the final picture.
- A depth-of-field effect that does not follow the thin-lens law (a uniform blur, or blur by pane index): test 7 checks the ordering.
- A reveal that cuts inside the payoff hold, or a view less than 30° off the rig axis during it (the panes then read as one picture again).
- Paintings loaded from image files, or painted by copying a named film's look: everything is computed in the run.

---

## Appendix A — Reference implementations (verified on this machine; use, extend or replace, and record)

### A.1 Seeded random numbers

```js
// mulberry32; one instance per simulation; draws in a fixed, documented order
export function mulberry32(seed) {
  let a = seed >>> 0;
  return function next() {
    a = (a + 0x6D2B79F5) >>> 0;
    let t = a;
    t = Math.imul(t ^ (t >>> 15), t | 1);
    t ^= t + Math.imul(t ^ (t >>> 7), t | 61);
    return ((t ^ (t >>> 14)) >>> 0) / 4294967296;
  };
}
export function gaussian(rng) { // Box–Muller, two draws, fixed order (make log and cos portable if the simulation is chaotic, §11.2)
  const u1 = Math.max(rng(), 1e-12), u2 = rng();
  return Math.sqrt(-2 * Math.log(u1)) * Math.cos(2 * Math.PI * u2);
}
```

### A.2 Easing

```js
// written with + − × ÷ only, so Node and the browser agree to the last bit (§6.1)
export const easeInOutCubic = x => { const y = -2 * x + 2; return x < 0.5 ? 4 * x * x * x : 1 - (y * y * y) / 2; };
export const easeOutQuint  = x => { const y = 1 - x; return 1 - y * y * y * y * y; };
export const clamp01 = x => Math.min(1, Math.max(0, x));
export const prog = (t, t0, d) => clamp01((t - t0) / d);
```

### A.3 Render driver (loopback server → headless Chromium on the GPU → verified capture → ffmpeg)

The page reserves an 8-CSS-pixel identity strip below the picture (viewport `W × (H + 8)`) and, at the end of `renderFrame(i)`, writes the frame index into 16 cells, most significant bit first:

```js
const strip = document.createElement('div'); strip.style.cssText = `position:absolute;left:0;top:${H}px;width:${W}px;height:8px;display:flex;`;
const cells = []; for (let k = 0; k < 16; k++) { const c = document.createElement('div'); c.style.cssText = 'flex:1;height:8px;background:#000'; strip.appendChild(c); cells.push(c); }
document.body.appendChild(strip);
const stamp = i => { for (let k = 0; k < 16; k++) cells[k].style.background = ((i >> (15 - k)) & 1) ? '#fff' : '#000'; };
// inside window.renderFrame(i): ... render the picture and the text ...; stamp(i);
```

```js
// tools/render.js  usage: node tools/render.js --format P --start 0 --end 675 --out renders/P_seg0.mp4 [--dsf 2] [--sw] [--page src/page.html]
import { chromium } from 'playwright';
import { spawn } from 'node:child_process';
import http from 'node:http'; import fs from 'node:fs'; import path from 'node:path';
import { mkdir, appendFile, readFile } from 'node:fs/promises';
const arg = (k, d) => { const i = process.argv.indexOf('--' + k); return i > 0 ? process.argv[i + 1] : d; };
const has = k => process.argv.includes('--' + k);
const SIZES = { P: [1080, 1920], L: [1920, 1080], S: [1080, 1080], LP: [1080, 1920], LS: [1080, 1080] };
const format = arg('format', 'P'); const [W, H] = SIZES[format]; const STRIP = 8;
const dsf = +(arg('dsf', 2)); const start = +arg('start', 0), end = +arg('end', 0);
const out = arg('out', `renders/${format}.mp4`); const identFile = out.replace(/\.mp4$/, '.ident');
const log = arg('log', out.replace(/\.mp4$/, '.log')); await mkdir(path.dirname(log), { recursive: true });
const L = s => appendFile(log, s + '\n');
// loopback static server: ES modules cannot be imported from file://; serves only files under the run directory
const root = process.cwd(); const mime = { '.html': 'text/html', '.js': 'text/javascript', '.mjs': 'text/javascript', '.json': 'application/json', '.ttf': 'font/ttf', '.bin': 'application/octet-stream' };
const srv = http.createServer((req, res) => { const p = path.normalize(path.join(root, decodeURIComponent(req.url.split('?')[0]))); if (!p.startsWith(root)) { res.writeHead(403); return res.end(); } fs.readFile(p, (e, d) => { if (e) { res.writeHead(404); return res.end(); } res.writeHead(200, { 'Content-Type': mime[path.extname(p)] || 'application/octet-stream' }); res.end(d); }); });
await new Promise(r => srv.listen(0, '127.0.0.1', r)); const port = srv.address().port;
const gpuArgs = ['--use-gl=angle', '--use-angle=vulkan', '--enable-features=Vulkan', '--ignore-gpu-blocklist'];
const browser = await chromium.launch({ headless: true, args: ['--force-color-profile=srgb', '--font-render-hinting=none', '--disable-lcd-text', ...(has('sw') ? [] : gpuArgs)] });
const page = await browser.newPage({ viewport: { width: W, height: H + STRIP }, deviceScaleFactor: dsf, colorScheme: 'dark' });
let lost = false;
page.on('pageerror', e => { L('PAGE ERROR ' + e); process.exitCode = 2; });
page.on('console', m => { const t = m.text(); L('CONSOLE ' + m.type() + ' ' + t); if (/context lost|DEVICE_LOST|CONTEXT_LOST/i.test(t)) lost = true; });
page.on('request', r => L('REQUEST ' + r.url()));
await page.goto(`http://127.0.0.1:${port}/${arg('page', 'src/page.html')}?format=${format}&dsf=${dsf}`);
await page.waitForFunction(() => window.__ready === true, null, { timeout: 120000 });
await L('RENDERER ' + await page.evaluate(() => window.__renderer || 'unknown'));
const cdp = await page.context().newCDPSession(page);
const ffArgs = ['-y', '-f', 'image2pipe', '-framerate', '60', '-c:v', 'png', '-i', '-',
  '-filter_complex', `[0:v]split=2[a][b];[a]crop=${W * dsf}:${H * dsf}:0:0,scale=${W}:${H}:flags=lanczos+accurate_rnd+full_chroma_int:out_color_matrix=bt709:out_range=tv[v];[b]crop=${W * dsf}:${STRIP * dsf}:0:${H * dsf},scale=16:1:flags=area,format=gray[id]`,
  '-map', '[v]', '-c:v', 'libx264', '-preset', 'slow', '-crf', '17', '-pix_fmt', 'yuv420p', '-profile:v', 'high', '-g', '120', '-keyint_min', '60', '-movflags', '+faststart', '-colorspace', 'bt709', '-color_primaries', 'bt709', '-color_trc', 'bt709', '-color_range', 'tv', out,
  '-map', '[id]', '-f', 'rawvideo', identFile];
await L('FFMPEG ffmpeg ' + ffArgs.join(' '));
const ff = spawn('ffmpeg', ffArgs, { stdio: ['pipe', 'ignore', 'inherit'] });
const write = buf => new Promise((res, rej) => ff.stdin.write(buf, e => (e ? rej(e) : res())));
if (start > 0) await page.evaluate(s => { for (let k = 0; k < s; k++) window.renderFrame(k, { draw: false }); }, start); // establish histories
for (let i = start; i < end; i++) {
  const t0 = Date.now();
  await page.evaluate(i => window.renderFrame(i), i);
  if (lost) { await L('CONTEXT LOST at frame ' + i); process.exit(3); }
  // clip.scale must equal the device scale, or the capture silently comes back at CSS-pixel resolution
  const { data } = await cdp.send('Page.captureScreenshot', { format: 'png', optimizeForSpeed: true, captureBeyondViewport: false, clip: { x: 0, y: 0, width: W, height: H + STRIP, scale: dsf } });
  await write(Buffer.from(data, 'base64'));
  await L(`frame ${i} ${Date.now() - t0}ms`);
}
ff.stdin.end(); await new Promise(r => ff.on('close', r));
await browser.close(); srv.close();
// identity check: every captured frame must carry its own index; a mismatch means a stale capture: re-render the segment
const id = await readFile(identFile); const n = id.length / 16; const bad = [];
for (let k = 0; k < n; k++) { let v = 0; for (let b = 0; b < 16; b++) v = (v << 1) | (id[k * 16 + b] > 127 ? 1 : 0); if (v !== start + k) bad.push([start + k, v]); }
await L(`IDENTITY frames ${n} expected ${end - start} mismatches ${bad.length}`);
process.exitCode = (n === end - start && bad.length === 0) ? (process.exitCode || 0) : 4;
```

Segments: P and S `[0,675)`, `[675,1350)`, `[1350,2025)`, `[2025,2700)`; L `[0,1350)`, `[1350,2700)`, `[2700,4050)`, `[4050,5400)`; at most two render processes at once (§11.4). Concatenate with the concat demuxer and `-c copy`. Verified here: 24 frames at 1× and 10 frames at 2× starting mid-film, every identity correct, BT.709 tv-range High profile output, and the speed-mode capture pixel-identical to `page.screenshot` at 2×; a frame from a mid-film segment matched the sequential render within 0.33/255 after encoding.

### A.4 WAV writer

```js
// 16-bit PCM stereo, 48 kHz; samples are Float64Array pairs in [-1, 1]
export function wavBuffer(left, right, rate = 48000) {
  const n = left.length, bytes = 44 + n * 4, b = Buffer.alloc(bytes);
  b.write('RIFF', 0); b.writeUInt32LE(bytes - 8, 4); b.write('WAVE', 8); b.write('fmt ', 12);
  b.writeUInt32LE(16, 16); b.writeUInt16LE(1, 20); b.writeUInt16LE(2, 22); b.writeUInt32LE(rate, 24);
  b.writeUInt32LE(rate * 4, 28); b.writeUInt16LE(4, 32); b.writeUInt16LE(16, 34); b.write('data', 36); b.writeUInt32LE(n * 4, 40);
  for (let i = 0, o = 44; i < n; i++, o += 4) {
    b.writeInt16LE(Math.round(Math.max(-1, Math.min(1, left[i])) * 32767), o);
    b.writeInt16LE(Math.round(Math.max(-1, Math.min(1, right[i])) * 32767), o + 2);
  }
  return b;
}
```

Sample count: `frames / 60 × 48000` exactly (P/S 2,160,000; L 4,320,000; loops 480 × 800).

### A.5 Loudness normalization (two-pass, −2.0 dBTP) and mux

```bash
ffmpeg -hide_banner -i audio/P_raw.wav -af loudnorm=I=-14:TP=-2:LRA=11:print_format=json -f null - 2> audio/P_measure.txt
# read input_i, input_tp, input_lra, input_thresh, target_offset from the JSON block, then:
ffmpeg -hide_banner -y -i audio/P_raw.wav -af "loudnorm=I=-14:TP=-2:LRA=11:measured_I=<input_i>:measured_TP=<input_tp>:measured_LRA=<input_lra>:measured_thresh=<input_thresh>:offset=<target_offset>:linear=true:print_format=json" -ar 48000 audio/P_norm.wav 2> audio/P_norm.txt
ffmpeg -hide_banner -y -i renders/P_video.mp4 -i audio/P_norm.wav -map_metadata -1 -c:v copy -c:a aac -b:a 192k -ar 48000 -ac 2 -shortest -movflags +faststart deliverables/multiplane-camera_P.mp4
```

### A.6 Contact sheets and fixed frames

```bash
ffmpeg -hide_banner -y -i deliverables/multiplane-camera_P.mp4 -vf "fps=0.5,scale=270:-1,tile=6x4:padding=4:margin=4" -frames:v 1 qa/contact_P.png
ffmpeg -hide_banner -y -i deliverables/multiplane-camera_L.mp4 -vf "fps=0.5,scale=480:-1,tile=9x5:padding=4:margin=4" -frames:v 1 qa/contact_L.png
ffmpeg -hide_banner -y -i deliverables/multiplane-camera_S.mp4 -vf "fps=0.5,scale=270:-1,tile=6x4:padding=4:margin=4" -frames:v 1 qa/contact_S.png
ffmpeg -hide_banner -y -i deliverables/multiplane-camera_P.mp4 -ss T -frames:v 1 qa/frames/P_T.png
```

### A.7 Digit cells for the readout

Measure the width of each digit `0–9` at the readout size with a hidden span; take the maximum as the cell width; render the value as one `<span>` per character with `display:inline-block; width:<cell>px; text-align:center` for digits and natural width for `.`, `%`, units and `−`.

### A.8 A Three.js starting point (HDR chain, one tone mapping, a generated environment)

```js
import * as THREE from 'three';
import { EffectComposer, RenderPass, EffectPass, BloomEffect, DepthOfFieldEffect, VignetteEffect, NoiseEffect, ToneMappingEffect, ToneMappingMode, BlendFunction } from 'postprocessing';
export function makeRenderer(W, H, dsf) {
  const r = new THREE.WebGLRenderer({ antialias: false, powerPreference: 'high-performance', preserveDrawingBuffer: true, stencil: false });
  r.setPixelRatio(dsf); r.setSize(W, H); r.outputColorSpace = THREE.SRGBColorSpace; r.toneMapping = THREE.NoToneMapping; // tone map once, in the chain
  r.shadowMap.enabled = true; r.shadowMap.type = THREE.PCFSoftShadowMap; return r;
}
export function makeComposer(renderer, scene, camera, look) {
  const composer = new EffectComposer(renderer, { frameBufferType: THREE.HalfFloatType, multisampling: 0 });
  composer.addPass(new RenderPass(scene, camera));
  const grain = new NoiseEffect({ premultiply: true, blendFunction: BlendFunction.SCREEN }); grain.blendMode.opacity.value = look.grain;
  composer.addPass(new EffectPass(camera,
    new DepthOfFieldEffect(camera, { focusDistance: look.dof.focus, focalLength: look.dof.focalLength, bokehScale: look.dof.bokeh }),
    new BloomEffect({ intensity: look.bloom.intensity, luminanceThreshold: look.bloom.threshold, luminanceSmoothing: 0.2, mipmapBlur: true, radius: look.bloom.radius }),
    new VignetteEffect({ darkness: look.vignette, offset: 0.3 }), new ToneMappingEffect({ mode: ToneMappingMode.ACES_FILMIC }), grain));
  return composer;
}
export function makeEnvironment(renderer, look) { // reflections without any image asset
  const pmrem = new THREE.PMREMGenerator(renderer); const sky = new THREE.Scene();
  sky.add(new THREE.Mesh(new THREE.SphereGeometry(50, 32, 16), new THREE.ShaderMaterial({ side: THREE.BackSide,
    uniforms: { top: { value: new THREE.Color(look.env.top) }, bottom: { value: new THREE.Color(look.env.bottom) } },
    vertexShader: 'varying vec3 p; void main(){ p = position; gl_Position = projectionMatrix * modelViewMatrix * vec4(position,1.0); }',
    fragmentShader: 'uniform vec3 top, bottom; varying vec3 p; void main(){ float h = normalize(p).y * 0.5 + 0.5; gl_FragColor = vec4(mix(bottom, top, h), 1.0); }' })));
  const env = pmrem.fromScene(sky, 0.04).texture; pmrem.dispose(); return env;
}
```

This is a floor, not a look: kept as it is, it produces exactly the default look that §6.6 asks you to design out. The world, the palette and the light are yours to invent.

---

End of brief. Begin with §5.

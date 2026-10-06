# Production Brief — Jina

Studio production brief · single run · self-contained · jina · brief version 1.0

---

## 0. How to read this brief

This document is a complete production order for one short animated documentary and its companion cuts. You are the production studio: in sequence you act as researcher, director, pixel artist, cinematographer, technical director, compositor, composer, sound designer, subtitle editor, standards editor, quality-control lead and reviewer.

**The film.** A short film, drawn entirely in pixel art computed in this run, with a calm Persian voice-over, about Jina Mahsa Amini, who died in September 2022 three days after being detained in Tehran, and about the movement that followed under the words *Woman, Life, Freedom* — «زن، زندگی، آزادی», in Kurdish *Jin, Jiyan, Azadî*. About ten real, widely known images of that movement — photographs, a handwritten sign, a gravestone, murals, a banner, an anonymous art action — are redrawn by you, pixel by pixel, as one continuous film.

**The bar.** This film will be judged against the most striking moving images being made anywhere: feature-film title sequences, the finest animated documentaries, cinematic game art, and the masters of modern pixel art. The art rubric of §6.11 stops at 10 only because a scale needs an end; aim past it. Wherever this brief is silent, the answer is the more ambitious one that you can still finish, verify and deliver. A film that is correct but looks like a photograph run through a pixelation filter, or like a game cutscene, has failed this brief as surely as one with a wrong fact.

**Facts and fairness come first.** Everything said or shown as fact comes from §7. The narration is fixed word for word (§7.2): it states what is undisputed plainly, and gives every disputed matter with each side's account and its source. The picture keeps the same discipline (§6.8): it takes no side, stages no heroes or villains, and never shows what is disputed. The emotion of this film comes from restraint, light, and acts of care — never from persuasion.

**Time.** The whole production has 4 to 8 hours: aim to finish in about 6, and treat 8 hours after `started_utc` as a hard limit. Plan the run in `plan.md` before you build anything and adapt the plan at every stage — measure, re-project, and cut scope by the ladder of §10.13 when it runs long (§10.1). Ideas are reviewed while they are cheap — as a written treatment, as still frames, as short clips — and the full masters are rendered once, at the end. A true and beautiful film delivered in seven hours beats a perfect one that is never finished.

**Two layers.** The **fixed layer** is short and exact: the facts and the narration (§7.1, §7.2), the list of works and how each may be shown (§7.3), the depiction and safety rules (§6.7), fairness (§6.8), the pixel grid and provenance (§6.1, §6.3), the structure and its voice-free minimums (§6.5, §8), legibility (§6.4), the deliverables (§3) and the automated checks (§12). Everything the viewer looks at and listens to inside those limits is the **designed layer**, and it is yours: the world, its light and palettes, the drawing style, the staging and transitions, the camera, how each work is entered and left, the score and the ambience. §7.4 gives a creative brief — the heart of the film, the images that must land, and sparks from an art panel that has already discussed this film — not a blueprint.

**Reference pack.** A folder accompanies this brief at `<BRIEFS>/reference/woman-life-freedom/` (if it is not there, look for `reference/woman-life-freedom/` next to this file). It holds the research dossiers behind §7 (`research/`), the reference photographs of the works with their licence records (`references/`, one `.json` beside each image), and an index (`INDEX.md`). Read the index in Stage 0. The general library at `<BRIEFS>/reference/craft/` describes how great films and animations build depth, light, rhythm and wonder; skim it during look development. The brief always prevails; the dossiers explain the facts but never add facts to the film; the reference photographs are for looking only (§6.1).

**One pass, no questions.** This production is completed from start to finish in a single pass with no outside input: nothing is asked of anyone, no confirmation or approval is awaited, no options are offered for someone else to choose. Every choice this brief does not fix is a designed-layer decision, made through the treatment, look development and reviews of §10 and recorded in `decisions.md`. Things only the project owner can decide (rights clearances, a human listening check) are written to `open-items.md` and never block the run. Nothing is escalated except through the BLOCKED protocol of §14.6, which ends the run after its file is written.

**Tools.** Use any language, library or program that runs on this machine: Node, Python 3, GLSL, WebGL2, canvas, ffmpeg, numerical libraries. Create virtual environments and install what you need from npm or PyPI; record every package and version in `run.json`. Appendix A gives verified reference pieces (render driver, integer upscale, voice and transcription calls, loudness); use, extend or replace them, and record why. Nothing is handed to you as code; you write all of it.

Vocabulary: **must** = mandatory; **never** = prohibited; **record** = write to the named file in the run directory. "Frame" means a rendered image at a fixed integer index `i`, with time `t = i / 60` seconds. "Art pixel" = one pixel of the native grid (§6.3). "L" = landscape film, "P" = portrait film. "Work" = one of the redrawn images of §7.3. "Cue sheet" = the measured timing of every narrated sentence (§10.3), the master clock of the film.

---

## 1. Introduction

This brief produces a short animated documentary, «ژینا» (*Jina*). On 13 September 2022 the Guidance Patrol detained Mahsa Amini, whose family called her Jina, in Tehran over her hijab; she collapsed in a police facility and died in hospital on 16 September. How she died is disputed: Iranian authorities say she was not struck and attribute her death to an underlying illness; her family says she was healthy and was beaten; a UN fact-finding mission concluded that physical violence in custody led to her death, a finding Iran rejected. At her burial in Saqqez, according to reports, mourners chanted the Kurdish words *Jin, Jiyan, Azadî*; in Persian, *Zan, Zendegi, Azadi* spread to universities and cities across Iran; solidarity rallies followed in cities around the world. On her temporary gravestone, in Kurdish, were written the words «ژینا گیان تۆ نامری، ناوت ئەبێتە ڕەمز» — "Dear Jina, you will not die. Your name will become a symbol."

The film shows, without saying it, where that name has since been written: a private name in public places — on a stone, on a card held up at a rally, in a lock of hair held up to the sky, in lettering on banners, on walls in other countries. Pixel art is not decoration here: the square-Kufic lettering in which the slogan is often set is already a grid of pixels, and the word on the stone, *ڕەمز*, means both *symbol* and *code*.

The finished piece is a computed film: every pixel is decided by code written in this run — no photograph, texture, sprite sheet, scan or stock element enters it — and every redrawn work is credited by name. The tone is quiet, precise and humane: no hype, no exclamation, no slogans presented as claims, no call to the viewer to do anything.

---

## 2. The ambition

Produce the complete deliverable set of §3 within the time budget of §10.1, with every check of §12 passing, the three panel reviews and the final look of §13, and a finalized run directory as specified in §14. What excellent means here, in priority order:

1. **True and fair.** Every spoken sentence is §7.2's, verified by a round-trip transcription; every disputed matter carries every side; the picture shows nothing disputed and takes no side; a reviewer who did not build the piece can trace every fact to its source.
2. **Respectful.** No one is endangered, humiliated or impersonated: no identifiable private person, no minor, no re-enactment of suffering, Jina's face only where it already exists in the world and never animated (§6.7).
3. **Unforgettable.** The images of §7.4 — the hair that becomes her name, and the last word of the epitaph written at first light — are the ones a first-time viewer would describe to someone afterwards.
4. **Beautiful in every frame.** Light, depth, palette, cluster and motion that the best pixel artists and a leading animation studio would sign; every hero frame aims at 8.5 or above on the rubric of §6.11, every other frame at 7.5 or above.
5. **Legible.** The film is fully understood with the sound off through its burned-in subtitles; every subtitle and every drawn word reads at phone size.
6. **On the grid.** Every frame is an exact integer enlargement of a native art-pixel image (§6.3); nothing is blurred, resampled or mixed in pixel size.

---

## 3. Expected output

All paths are relative to the run directory `RUN` defined in §4. `N_L` and `N_P` are the frame counts fixed at the timing lock (§10.3) and recorded in `build/timeline.json`; every L deliverable has exactly `N_L` frames and every P deliverable exactly `N_P`.

| # | File | Spec |
|---|------|------|
| 1 | `deliverables/jina_L.mp4` | 3840×2160 (native 480×270 × 8), 60.000 fps, `N_L` frames (picture 195–215 s plus the 20.000 s credits gallery), H.264 High, yuv420p, bt709 tv range, AAC 256 kb/s 48 kHz stereo, −16 LUFS ±1, true peak ≤ −1.0 dBTP; no subtitles |
| 2 | `deliverables/jina_L_fa.mp4` | 1920×1080 (native × 4), same frames and audio, Persian subtitles drawn in Vazirmatn at the delivered size and composited over the × 4 enlargement (§6.4) |
| 3 | `deliverables/jina_L_en.mp4` | 1920×1080 (native × 4), same frames and audio, English subtitles burned in (§6.4) |
| 4 | `deliverables/jina_P.mp4` | 2160×3840 (native 270×480 × 8), 60.000 fps, `N_P` frames (picture 80–95 s plus the 8.000 s credits card), same codec and audio spec; no subtitles |
| 5 | `deliverables/jina_P_fa.mp4`, `deliverables/jina_P_en.mp4` | 1080×1920 (native × 4), Persian / English subtitles burned in |
| 6 | `deliverables/jina_L.fa.srt`, `.en.srt`, `.fa.vtt`, `.en.vtt`; the same four for P | Sidecar subtitles, UTF-8, times from the cue sheet (§10.3) |
| 7 | `deliverables/jina_poster_L.png`, `jina_poster_P.png` | PNG, sRGB, 3840×2160 and 2160×3840, the poster frame of §8.4, no text other than diegetic lettering |
| 8 | `deliverables/jina_master_native_L.mkv`, `jina_master_native_P.mkv` | Lossless archive: FFV1, rgb24, the native art-pixel frames (480×270 / 270×480) of the subtitle-free film |
| 9 | `deliverables/CREDITS.md`, `deliverables/LICENSE.md` | Every work, its creator, date, source and licence (§6.9); the film's licence |
| 10 | `deliverables/manifest.json`, `deliverables/README.md` | §14.1, §14.2 |
| 11 | `deliverables/owner_listening_sheet.md` | §14.4: the timestamps and words a Persian-speaking owner should check by ear, and how to swap a take without re-rendering the picture |
| 12 | `qa/qa_report.md`, `qa/probe_*.jsonl`, `qa/grid/*.json` | Every check of §12 with measured value, threshold, pass/fail |
| 13 | `reviews/review_1/`, `review_2/`, `review_3/`, `reviews/review_N_notes.md`, `reviews/final_look.md` | §13 |
| 14 | `build/script_fa.json`, `build/cue_sheet.json`, `build/timeline.json`, `build/look.json`, `build/strings.json` | §7.2, §10.3, §6.4 |
| 15 | `audio/voice/` (one WAV per sentence), `audio/voice/manifest.json`, `audio/voice/stt/` | §9.2, §10.3 |
| 16 | `plan.md`, `decisions.md`, `open-items.md`, `postmortem.md`, `lookdev/` | §10, §14 |

A run is complete only when every row exists, `qa/qa_report.md` shows every check PASS or failed-with-explanation (each with a `decisions.md` entry and an `open-items.md` row), and the final look of §13.4 is written — or when the 8-hour limit of §10.1 ended the run with every deliverable present and everything unfinished listed in `open-items.md`.

---

## 4. Where to store things

Base directory (fixed): `<OUTPUT>/`

Run directory: `RUN = <OUTPUT>/jina/run-<YYYYMMDD-HHMMSS>/` where the timestamp is the UTC start time of this run, taken once at the beginning (`date -u +%Y%m%d-%H%M%S`) and never changed. Create it with `mkdir -p`. If the base directory is not writable, stop and follow §14.6. Never write outside `RUN` except for the package caches that npm, pip and Playwright manage themselves; scratch files go under `RUN/tmp/`.

Layout inside `RUN` (create all folders at the start):

```
RUN/
  run.json            # start time, host, tool versions, renderer string, seed, brief version, voice availability
  plan.md             # the time plan: planned and actual time per stage, re-projections, scope cuts (§10.1)
  decisions.md        # every judgment call, with the reason (append-only; headings carry `date -u` time)
  open-items.md       # anything unresolved that needs the project owner's decision
  postmortem.md
  src/                # the engine, scenes, palettes, pixel maps, text rasteriser, page(s), shaders
  tools/              # render driver, upscale/encode, subtitle burner, QA and helper scripts
  audio/              # voice/, score/, ambience/, stems, mixes
  assets/fonts/       # the three Persian fonts of §5 item 5 (and nothing else)
  build/              # script_fa.json, cue_sheet.json, timeline.json, look.json, strings.json, animatics, native frames
  lookdev/            # treatment.md, reading_sheets/, iter_1 … iter_N/, selected.md
  renders/            # native frame captures (lossless), identity files, per-segment logs
  qa/                 # qa_report.md, probes, grid/, contact sheets, frames/
  reviews/            # review_1 … review_3/, review_N_notes.md, final_look.md
  deliverables/       # final files only
  tmp/                # scratch
```

The reference photographs are never copied into `RUN`; they are opened where they are, for looking (§6.1).

File naming: lower-case, words separated by `_`, no spaces, no dates in deliverable names. Final files are exactly the names in §3.

---

## 5. Prerequisites and pre-flight

Run these checks first and record the results in `run.json`. Fix what can be fixed; otherwise follow §14.6.

1. `node -v` v20 or later; `npm -v`; `python3 --version` 3.10 or later with pip (a virtual environment under `RUN/.venv` is recommended); `python3 -c "import PIL, numpy"` after installing them.
2. `ffmpeg -version` and `ffprobe -version` 5.0 or later; encoders `libx264`, `aac` and `ffv1` listed; filters `loudnorm`, `ebur128` and `scale` (with `flags=neighbor`) available.
3. Browser: `npm i playwright` then `npx playwright install chromium` (record versions). If the download fails, use the system Chrome or Chromium (`channel: 'chrome'` or `executablePath`); record which.
4. GPU: launch headless Chromium with the flags of Appendix A.3 and read the WebGL2 renderer string. Record it as `gpu_renderer`. Rendering at the native grid is light; a software renderer (`SwiftShader`) is acceptable here — record it and multiply the render estimates of §15 by two.
5. Fonts: copy from `fonts/persian/` beside this brief into `assets/fonts/`, with their licence files, and verify size and SHA-256:
   - `erfan-pixel/erfan.ttf` — 30,248 bytes, `bc8d6a20feff07958e85f7f36553c661d682902e8f8ce7f3798d01a4e5c90057`, SIL OFL 1.1. A Persian pixel font on a 16-pixel grid with Persian digits and basic Latin; it has no Sorani-only letters (ێ ە ڕ ۆ ڵ).
   - `vazirmatn/Vazirmatn[wght].ttf` — 241,328 bytes, `696249a2c74b39ffdef55de4df2809c5b639d3ff80d618d8160a095d2fd49dca`, SIL OFL 1.1. Covers Persian, Sorani, Persian digits, ZWNJ, Latin.
   - `noto-nastaliq-urdu/NotoNastaliqUrdu[wght].ttf` — 690,304 bytes, `98a4787f34eb6fde57fb9a1121a8f216301196ab0da98ea110cad581be8abbcd`, SIL OFL 1.1. Nastaliq, for at most one title word.
   If one is missing or wrong, record it; Vazirmatn alone is sufficient for every text task.
6. Voice service: the file `<CREDENTIALS_FILE>` contains one line `ELEVENLABS_API_KEY=<key>`. Read the key from that file at call time; never copy it into the run directory, a log, a manifest or a commit. Verify `GET https://api.elevenlabs.io/v1/models` (header `xi-api-key`) returns 200 and lists `eleven_v4` (or `eleven_v3`) with Persian among its languages, and that `GET /v1/shared-voices?language=fa` returns voices. Record `voice_available: true|false` with the HTTP statuses. If the voice service is unavailable after two attempts, follow §9.2's fallback.
7. Network use is limited to the npm registry, PyPI, the Playwright browser CDN and the voice service of item 6. Everything the film needs is in this brief, the `fonts/` folder and the reference pack.
8. Machine: this is a laptop with an integrated GPU that is lost under heavy parallel load (§11.4). Check `free -g` (at least 8 GB available before any render), `df -h` (about 20 GB free), and that no other production is rendering (`pgrep -af "chrome|ffmpeg"`); if one is, wait for it to finish.
9. Create `run.json` with: `brief: "jina"`, `brief_version: "1.0"`, `started_utc`, `host`, `gpu_renderer`, `node`, `npm`, `python`, `ffmpeg`, `packages`, `browser`, `voice_available`, `fonts` (name, bytes, sha256 each), `seed: 20260928`.

---

## 6. Studio standards

### 6.1 Technology — what is fixed, what is free

Fixed interfaces and guarantees:

- **Everything visible is drawn in this run.** No external image, texture, sprite, model, video, scan or environment map enters the film, and no file under the reference pack is ever read by any build, render or audio code. The only files the page may load are your own code and the fonts of §5 item 5. This is checked (gate F01).
- **Looking is allowed; deriving is not.** You may open the reference photographs and study them as long as you like. From each work you may write a **reading sheet** in `lookdev/reading_sheets/<work>.md`: up to 40 landmarks in normalized coordinates (horizon, eye line, the tip of a lock of hair, the edges of a stone), gesture angles, the composition's thirds, and at most 6 colour seeds written as numbers that you then redesign into your own ramps. You may never: load a reference image in code; downscale, quantize, cluster, trace, edge-detect, vectorize, mask, depth-estimate or colour-sample it by program; project it under your drawing; or transcribe its text (all text comes from §6.4's verified strings). Every work is **redrawn**, not converted: geometry authored in code, rasterized to the art-pixel grid, cleaned into clusters, with hand-authored pixel maps (string maps in code, e.g. rows like `"..aBBa.."`) for faces, hands, glyphs, catchlights and every detail that carries meaning.
- **Frame-index time.** The whole picture and the subtitles are a pure function of the frame index `i`. Never use wall-clock time, `requestAnimationFrame` timing, `Math.random`, or timers to drive anything visible. Randomness comes only from the seeded generator of Appendix A.1 (`mulberry32`, seed `20260928`), drawn in a fixed, documented order; shader noise hashes position and frame index.
- **Indexed colour.** Each frame is composed as palette indices and resolved through a palette at the end, so every output pixel is a palette entry (§6.3).
- **Capture.** Each frame is captured at its native art-pixel size (480×270 or 270×480), losslessly, with a verified frame identity (§11.3, Appendix A.3), and enlarged afterwards by an exact integer factor with nearest-neighbour sampling (Appendix A.4). Never capture at the output size and never let the browser scale the art.
- **Encoding.** libx264 High, `-preset slow -crf 12 -tune animation -pix_fmt yuv420p -g 120 -keyint_min 60 -movflags +faststart`, bt709 primaries, matrix and transfer, tv range (`out_color_matrix=bt709:out_range=tv` in the scale filter); audio muxed separately (AAC 256 kb/s, 48 kHz, stereo).
- **Determinism.** Two independent renders of the same frame are identical at the native size (gate B02: 0 differing pixels).

Free (designed, recorded in `build/look.json` and `decisions.md`): the rendering technology (WebGL2 with custom GLSL into integer render targets, canvas 2D on an indexed buffer, or a hybrid), the scene construction (orthographic or parallax layers, simple 3-D primitives rasterized to the grid, signed-distance shapes), lighting (quantized normal-mapped light, colour cycling, volumetrics at native resolution), simulation of hair, cloth, smoke and water, how scenes are composed and transitioned, and how the work is parallelized within §11.4.

### 6.2 Formats

| Format | Native grid | Delivered | Picture | Credits | Content |
|---|---|---|---|---|---|
| L | 480×270 | 3840×2160 (× 8); `_fa`, `_en` at 1920×1080 (× 4) | 195–215 s | 20.000 s gallery | Beat sheet §8.1, the full narration |
| P | 270×480 | 2160×3840 (× 8); `_fa`, `_en` at 1080×1920 (× 4) | 80–95 s | 8.000 s card | Beat sheet §8.2, the portrait narration |

P is not a crop of L: it is a second camera on the same drawn worlds, with its own compositions, built at its own native grid. Never letterbox, pillarbox or crop one film to make the other. The picture lengths are set at the timing lock (§10.3) from the measured narration and then never change.

### 6.3 The pixel grid (fixed)

- **One art-pixel size per frame.** Every delivered frame — apart from the subtitles of the `_fa` and `_en` versions (§6.4) — is the exact integer enlargement of one native image (L 480×270, P 270×480): every block of 8×8 (or 4×4) output pixels is a single colour, aligned to the frame origin (this film uses no output-space offset). A change of art-pixel size is allowed only as a full-frame event (every pixel of the frame at the new size, each step redrawn, never resampled), at most twice in the film, and declared in `look.json`.
- **Palette.** You design the palettes (per scene, with anchors shared across the film). Each shot declares keyed palettes of at most 48 entries in `look.json`. The palette in force at frame `i` is a pure function `palette(i)` of `look.json` — a keyed palette, a blend between two keys at a declared weight (dusk to night), or a cycling rotation — and the renderer exports that function. Every pixel of a frame is an entry of `palette(i)`. During a declared transition between two shots the frame may use the union of the outgoing and incoming palettes (at most 96). The credits gallery uses one gallery palette of at most 48 entries, into which every thumbnail is redrawn (gate B04).
- **No blended pixels.** No alpha crossfades between images, no bilinear or bicubic sampling, no GPU anti-aliasing, no mipmaps, no blur, bloom, depth of field or grain applied as a filter over the art. Light, haze, glow and focus are drawn — quantized to palette steps, dithered with ordered or blue-noise patterns anchored to their layer — never filtered. Error-diffusion dithering is never used on anything that moves.
- **No bitmap transforms.** Never rotate, scale or skew a rasterized image. Things that turn or grow are re-rasterized from their geometry every frame (or redrawn as new pixel maps). Cameras and layers move in whole art pixels.
- **Motion.** Delivery is 60 fps. Every drawn element (figure, hair, cloth, smoke, fire, water, crowd, placard) has a declared drawing rate and changes its pixels only on its drawing frames: a hold of 2 to 8 frames per drawing (30 to 7.5 drawings per second), or longer. Simulations may step every frame but are drawn only on the element's drawing frames. Every frame may change: integer camera and layer steps, palette blends and cycling, quantized light, and the tip of a line while it is being drawn. Sub-pixel motion is made by changes of quantized coverage on drawing frames, never by per-frame interpolation of pixels (gate B05).

### 6.4 Text and legibility (fixed limits, designed style)

**The text of the film is almost nothing.** Inside the picture only diegetic lettering appears — words that exist on the works themselves — plus, at most, one title word and one date card. Facts and numbers are spoken, never shown as type. Subtitles exist only in the `_fa` and `_en` versions and in the sidecars.

**Verified strings (`build/strings.json`, copied verbatim from this table; every drawn or typeset string in the film must be one of these, byte for byte after Unicode NFC normalization, gate D01).**

| id | string | where it may appear |
|---|---|---|
| T1 | «ژینا گیان تۆ نامری» (line 1) and «ناوت ئەبێتە ڕەمز» (line 2) — together the epitaph «ژینا گیان تۆ نامری، ناوت ئەبێتە ڕەمز» | The handwritten epitaph (Sorani Kurdish). Its letters are drawn as handwriting by your own pixel maps — no font has to supply them. Declared partial states: line 1 alone; line 1 with «ناوت ئەبێتە» (the unfinished sentence); any in-progress stroke of these. The sign photographed in Ontario (reference 05) is a handwriting reference only: its spelling of the second word (دەبێتە) differs from the stone's, and the film always draws the stone's wording. |
| T2 | «ژینا» | The name on the book-shaped headstone (reference 04), and the name the hair forms (§7.4) |
| T3 | «مهسا» | The calligraphic name on the grave frame (reference 03) |
| T4 | «زن زندگی آزادی» | Your own square-Kufic setting of the slogan; the Persian line of the trilingual banner (reference 17) |
| T5 | `FRAU · LEBEN · FREIHEIT` | The Berlin banner (reference 07); `FRAU LEBEN FREIHEIT` and `WOMAN LIFE FREEDOM` on the trilingual banner (17) |
| T6 | `JIN JIYAN AZADÎ` | The Frankfurt mural (reference 14), as three stacked words |
| T7 | `Freiheit` | The flower band of the Berlin-Friedrichshain mural (reference 15) |
| T8 | «ژینا» in Nastaliq (optional title, once) | A title, if the design uses one |
| T9 | «۲۲ شهریور ۱۴۰۱» with `13.09.2022` (optional date card, once) | The one date card, if the design uses one |
| T10 | The credits of §6.9, the subtitle cues of §7.2, the film's licence line | The credits gallery/card; the subtitle tracks |

Every other piece of lettering visible in a source — placards, flags, leaders' portraits, a hashtag, sponsors, watermarks, private names, the verse carved above the name on the headstone — is drawn illegible (shapes and colour only) or left out.

**Rendering Persian and Kurdish text** (traps verified on this machine):
- Typeset strings (T3–T9, the credits) are shaped whole, never letter by letter, and revealed by a moving mask (right to left), never by growing the string or by letter-spacing. Handwritten strings drawn from your own pixel maps (T1, and T2 when the hair forms it) are exempt: they may be written in stroke order — strokes, then dots and hatching — as a hand writes, provided every completed state is a verified string or one of T1's declared partial states.
- Erfan is drawn exactly at 16, 32 or 48 native pixels (its 16-pixel grid); any other size breaks it; it cannot join ZWNJ compounds, so use it only for strings without ZWNJ (the date card T9 at 32 px is ideal). Vazirmatn and Nastaliq rasterized at native size are thresholded to palette colours with hand cleanup; check that every letter dot survives (gate D03). Nastaliq needs a line height of at least 2.
- Persian digits (۰–۹) for Persian text; ZWNJ preserved; Persian ی and ک only (never Arabic ي ك).

**Subtitles — the one declared exception to the grid.** Subtitles are an accessibility layer, not part of the drawing, and they are the only element drawn at the delivered resolution instead of on the art-pixel grid. Tested on this machine: Erfan at 16 native pixels is too small to read on a phone, breaks ZWNJ compounds (it has no ZWNJ in its character map: «نمی‌میری» joins into one word) and draws the Persian comma and Latin letters poorly; at 32 native pixels it is beautiful but a 38-character line no longer fits the portrait frame. So: Persian and English cues in **Vazirmatn** (weight 500–700), anti-aliased, drawn at the delivered size of the `_fa`/`_en` version and composited over the enlarged frame — L (1920×1080): Persian 56 px, English 48 px; P (1080×1920): Persian 52 px, English 46 px (±8 %; measured: the longest cue line of §7.2 is 945 px wide in L and 878 px in P at these sizes, inside 90 % of the frame width). At most 2 lines per cue (as §7.2 breaks them; never re-wrapped); centred; inside the bottom 22 % of the frame and above the bottom 6 % (P: inside the band from 62 % to 85 % of the height, clear of phone player controls); legibility by a soft dark outline or a quiet backing band reaching a contrast of 4.5:1 (gate D04). Each cue appears at its sentence's start, splits evenly across the sentence when the sentence has two cues (by character count), and leaves 0.3 s after the sentence ends (or when the next begins); no cue during a voice-free span. Cue texts are §7.2's `sub_fa` and `sub_en`, verbatim. Because each cue is constant over its span, render each cue once as a transparent image at the delivered size and overlay it for its frames.

### 6.5 The structure (fixed order, flexible timecodes)

The L film has nine beats and a credits gallery; P has seven beats and a credits card (§8). The beat order, each beat's narration (§7.2), its works (§7.3), its duration range and its voice-free minimum are fixed. Exact timecodes are not: they are computed at the timing lock (§10.3) from the measured duration of every narrated sentence, written to `build/timeline.json`, and from then on everything — picture, music, subtitles, checks — is placed by that file.

Timing rules (gate E01–E05):
- No narration over the first 1.5 s after a work first appears, and none in the first 0.5 s after any cut.
- Gaps between sentences inside a beat: 0.4–0.9 s; between beats: at least 1.2 s.
- No more than 20 s of continuous voice anywhere.
- At least 30 % of the picture (excluding the credits) has no voice.
- Each beat's voice-free minimum (§8) is a single unbroken span with no voice and no subtitle.
- If the measured narration makes the picture exceed its maximum, follow §10.3's cut order; if it falls short of the minimum, lengthen holds — never add words, never stretch audio by more than 4 %.

### 6.6 Picture language (designed, within the limits of §6.3 and §6.7)

- **One film, not a slideshow.** The works are linked into one continuous film: every transition is motivated by a form, a light or a gesture present on both sides of it. There are at most two hard cuts in the whole film, each declared in `look.json`. Transitions stay on the grid: dither-threshold dissolves shaped by an image's own forms, palette morphs, a line or thread that carries the eye from one work into the next, pixels that gather and re-form — never an alpha crossfade.
- **Camera.** Framing, parallax depth, slow tracks and push-ins (by parallax, or by redrawing at a closer framing — never by scaling a bitmap), reveals and changes of scale are designed. A still frame of any shot must read as a composed image.
- **Light, world, style.** Lit dioramas, engraving-like line work, colour-cycled atmospheres, monochrome passages, or a style no one has named — at the highest level. Each redrawn work keeps what makes it recognisable within one second (§7.3) and is unmistakably a new drawing.
- **Tells of a cheap or default look, to be designed out:** a photograph pixelated by averaging (muddy clusters, noise, lost eyes); mixed pixel sizes; filter-on-top bloom or blur; pillow shading; jagged lines and stray single pixels; dithering that swims; game-like bounce, chibi proportions, saturated primaries, "8-bit" sound; a centred subject in every shot; motion without hierarchy; dead holds.
- **Safety.** No more than 3 luminance flashes per second (gate C01); no strobing patterns over large areas.

### 6.7 Depiction, dignity and safety (fixed)

1. **Never shown, in any form:** the arrest, the van, the custody facility's interior, the collapse, the hospital interior or a hospital bed, any injury, blood, weapons being used, force against anyone, a body. The disputed moments are spoken over places — a street at evening, a closed door, a lit window, an empty frame — never illustrated.
2. **Jina's face** appears only where it already exists in the world: the portrait behind the glass of her grave (reference 03), the murals of Frankfurt and Berlin-Friedrichshain (14, 15) in their painters' styles, and, at small scale, the portraits repeated on placards (07, 10, 16). Never a standalone re-creation of her family photograph; never full-frame; never animated — no blink, breath, lip movement, turn or expression; only the light and the world around it move. Where her face is drawn as a likeness (W2, W11, W12), the likeness is defined once (proportions and landmarks in a single reading sheet) and drawn anew for each work in that work's own pose, angle and medium, so that the three agree as one person; face at least 48 art pixels tall in its closest view; every eye and mouth pixel is checked at delivered size. On placards (W9, W10) her portrait is a small mark under 16 art pixels — hair, scarf and face in at most three tones, no eye or mouth pixels — not a likeness.
3. **Private people** are never identifiable: seen from behind or in silhouette (any size, the face carrying no features), or with faces of at most 8 art pixels and no features drawn. Minors are never depicted. Only the hands the works contain are shown (the raised hand with the lock and the lowered hand with the scissors in W7; the hands holding sheets in W9); no gesture is invented.
4. **Security forces**, where they exist in a source (reference 02), appear only as distant silhouettes in the same light, scale and drawing language as everyone else — never lit, framed or scored as menace; protesters are never staged as heroes.
5. **Remove from the sources:** the second woman in reference 06 (stage-blood make-up and a rope), the child's hands at the edge of reference 03, the dates and small text on the grave stone, the hashtag on the sign (05), every legible placard, every flag (no national, regional, party or movement flag is identifiable anywhere in the film), every portrait of a political figure, every watermark and sponsor mark.
6. **Red** is never a fill that reads as blood. The red of the fountains (§7.3 W8) is a deep, still maroon; red otherwise appears only where it is the literal colour of a source's lettering.
7. **No sound of violence** (§9.1).

### 6.8 Honesty and fairness (fixed)

- Every spoken sentence is §7.2's, in order, word for word; nothing else is spoken. Every drawn word is a verified string (§6.4). No number is shown on screen.
- Every disputed matter is given with every side named in §7.2; in beat 3 the three accounts — the authorities, the family, the UN mission with Iran's rejection — get **equal treatment**: the same picture grammar (one composition in three states of light, or three equivalent frames), the same kind of change between them, no music, no camera move or detail that favours one; the three states form no progression — no brightening or darkening trend, no movement toward dawn, no warming or cooling across them, the third interchangeable in value and colour temperature with the first; and no account's span (its sentences plus its hold) shorter than 70 % of the longest — the family's eight words are held, not hurried (gate E04).
- Music is silent under every sentence that states a death (§7.2 marks them `death: true`) and under beat 3 (gate G05).
- The red fountains (W8) never appear in beat 6 or within 10 s of any sentence marked `death: true`; they are shown in beat 5, voice-free, as one of the art actions of October 2022, already red as the action left them — never red flowing, spreading or filling on screen (gate E06).
- Beauty is added by light, drawing, staging and sound — never by inventing an event, a gesture, a face, an expression, a word, or a detail that suggests a version of what happened.
- The film does not end on a slogan, a raised fist, a flag, a sunrise crane-up or a musical triumph.

### 6.9 Credits and licence (fixed)

- The L film ends on a **credits gallery** of 20.000 s: every work shown returns small, with its title, creator, year and licence, and the line *"Redrawn as pixel art. Every frame computed."* in Persian and English (both strings are in §7.3). P ends on an 8.000 s card with the same information compressed.
- `deliverables/CREDITS.md` lists every work with title, creator, date, source URL and licence exactly as in §7.3, and the fonts with their licences. Unknown mural painters are credited as unknown.
- Several sources are licensed CC BY-SA, so the film as a whole is released under **CC BY-SA 4.0**; `LICENSE.md` says so and names the share-alike sources.

### 6.10 The poster

One frame per format — the image that must land (§7.4) at its most beautiful — exported as PNG at the delivered master size from the native frame by the integer enlargement. It contains no text except diegetic lettering.

### 6.11 The art rubric

Used in look development (§10.6) and by the panel (§13). Each line is scored 0–10: **10** stands beside the best title sequences, animated documentaries and pixel art made anywhere; **9** a leading studio's finished work; **8.5** this studio's floor for a hero frame; **7.5** the floor for every other frame; **5** correct but unlit, unstaged, default; **3** a photograph through a pixelation filter, or a game asset dropped into a frame; **0** broken.

| # | line | what is judged |
|---|---|---|
| 1 | Wonder | would a stranger stop and look; is there something here they have not seen before |
| 2 | Light | a key light you can name, colour temperature, highlights and shadows that obey it, drawn glow; nothing flat or pillow-shaded |
| 3 | Depth and air | planes separated by value, haze, parallax and scale; the frame has air |
| 4 | Pixel craft | deliberate clusters, palette ramps, hand anti-aliasing, selective outlines, dithering that does not swim; drawn at this grid, not degraded from a bigger image |
| 5 | Composition | one focal point; the eye knows where to go; negative space; reads on a phone |
| 6 | Camera and transition | every shot has an intention; every transition carries meaning (a thread, a light, a form) and stays on the grid |
| 7 | Motion | sub-pixel life in the holds; secondary motion in hair, cloth, smoke, light; calm beats calm on purpose; nothing moves without a reason |
| 8 | Recognition | each work reads within one second as itself and unmistakably as a new drawing |
| 9 | Coherence | palette, light and drawing belong to one film across beats and both formats |
| 10 | Dignity and truth | nothing shown suggests a version of a disputed event; no one is made a hero, villain, victim-spectacle or icon; the emotion comes from restraint and care |

Be hardest on lines 1, 2, 3, 4 and 10. A score is worth recording only with the sentence that justifies it.

---

## 7. The subject

### 7.1 What happened, and where it comes from (fixed; the only facts of this film)

The facts below were assembled from primary documents and multiple independent sources, each attributed; the full dossiers, with claim numbers and source links, are in `reference/woman-life-freedom/research/`. The narration of §7.2 uses only these facts. Where sources disagree, the narration gives each account with its source, and the picture shows none of them.

**Undisputed.** Mahsa Amini, whom her family called by her Kurdish name Jina, was a young woman from Saqqez in Iran's Kurdistan province. On the evening of 13 September 2022 (22 Shahrivar 1401) the Guidance Patrol (*gasht-e ershad*) detained her in Tehran in connection with her hijab and took her to a police facility on Vozara Street. There she collapsed; she was taken to Kasra Hospital, remained in a coma, and died on 16 September 2022 (25 Shahrivar 1401). She was buried on 17 September 2022 (26 Shahrivar 1401) in Aichi cemetery, Saqqez. Her temporary gravestone carried, in Sorani Kurdish, «ژینا گیان تۆ نامری، ناوت ئەبێتە ڕەمز» ("Dear Jina, you will not die. Your name will become a symbol"); the Persian «ژینا جان تو نمی‌میری، نامت یک رمز می‌شود» is a published translation, not the inscription.

**Disputed — the cause of her death.** Iranian authorities (the police, a parliamentary commission, and the state Legal Medicine Organization in its report of 7 October 2022) say she was not struck and attribute her death to an underlying condition linked to brain surgery in childhood. Her family says she was healthy and was beaten. The UN Independent International Fact-Finding Mission on Iran concluded in March 2024 that she "was subjected to physical violence that led to her death" in custody. Iran rejected that finding.

**The movement.** "Woman, Life, Freedom" — Kurdish *Jin, Jiyan, Azadî*, Persian *Zan, Zendegi, Azadi* — has roots in the Kurdish women's movement decades before 2022. According to reports, mourners chanted it at her burial in Saqqez. Its Persian form spread with the protests to universities and cities across Iran; Iranian authorities called the protests «اغتشاشات» (riots) and the work of foreign enemies. Death tolls are reported by source and never merged: an IRGC commander said in November 2022 that more than 300 people had died, including security forces; the non-governmental Iran Human Rights recorded the deaths of at least 551 protesters, and the UN mission called a figure of 551 credible. Solidarity rallies were held in many cities outside Iran, among them Berlin on 22 October 2022 (about 80,000 people by a police estimate). According to media reports, street protests gradually subsided, while many women continued to be seen in public without a headscarf. Parliament passed a new hijab law; since December 2024 (Azar 1403) its implementation has been halted by decision of the Supreme National Security Council; hijab remains compulsory under the existing rules.

**What this film leaves out on purpose:** her exact age and birth date (sources disagree); "heart attack" as an official cause (that was early police wording, not the coroner's finding); any claim that the inscription was ordered removed; every event after 2024 other than the law's continued suspension; any single merged death toll or execution total; any slogan presented as a claim.

### 7.2 The narration (fixed, word for word)

The narration was written in calm, formal Persian for reading aloud, checked sentence by sentence against the sources by an independent standards editor, and verified against primary documents (the UN mission's report, the Legal Medicine Organization's statement, the IRGC commander's statement, the rights group's count, the Supreme National Security Council's decision, and others; the verification log is in `reference/woman-life-freedom/research/`). It is fixed: never add, drop, reorder or reword a sentence, except by the optional cut order inside the JSON, applied in its order and recorded. Every sentence is generated from its `tts` text (numbers and dates written as words, ZWNJ, diacritics only on homographs) and shown in subtitles from `sub_fa` and `sub_en`. Sentences marked `death: true` state a death: music is silent under them (§6.8).

Word choices that keep it neutral, for reference: «اعتراضات» (protests) — the authorities' word «اغتشاشات» (riots) appears only inside their attributed statement; «درگذشت» / «جان باختن» for death, never «قتل» or «شهید»; «نیروهای امنیتی» for security forces; «در ارتباط با حجابش» (in connection with her hijab) rather than the police's charge; «بنا بر گزارش‌ها» / «به گزارش رسانه‌ها» where a fact rests on reports; the three accounts of her death in the order they were stated, each with its source, and Iran's rejection of the UN finding directly after it; the epitaph spoken only in Persian translation, introduced as a translation. A Kurdish-speaking listener should check the three Kurdish words of B4.1 (if the take sounds Persianized, the cut order's step 1 replaces the sentence).

**Landscape (L) — 225 words as written, 245 as spoken**

| id | beat | Persian (display) | English | death |
|---|---|---|---|---|
| B2.1 | `jina` | <span dir="rtl">مهسا (ژینا) امینی، زن جوان کردی از سقز بود.</span> | Mahsa (Jina) Amini was a young Kurdish woman from Saqqez. |  |
| B2.2 | `jina` | <span dir="rtl">۲۲ شهریور ۱۴۰۱، گشت ارشاد او را در تهران، در ارتباط با حجابش، بازداشت کرد.</span> | On 22 Shahrivar 1401 [13 September 2022], the Guidance Patrol detained her in Tehran in connection with her hijab. |  |
| B2.3 | `jina` | <span dir="rtl">در مقر پلیس از حال رفت و سه روز بعد در بیمارستان درگذشت.</span> | She collapsed at the police facility and died in hospital three days later. | yes |
| B3.1 | `accounts` | <span dir="rtl">مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.</span> | Iran's authorities say she was not beaten, and they attribute her death to an underlying illness. |  |
| B3.2 | `accounts` | <span dir="rtl">خانواده‌اش می‌گویند او سالم بود و کتک خورد.</span> | Her family says she was healthy and was beaten. |  |
| B3.3 | `accounts` | <span dir="rtl">هیئت حقیقت‌یاب سازمان ملل در اسفند ۱۴۰۲ نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید.</span> | In Esfand 1402 [March 2024], the UN fact-finding mission concluded that physical violence in custody led to her death. |  |
| B3.4 | `accounts` | <span dir="rtl">ایران آن را رد کرد.</span> | Iran rejected it. |  |
| B4.1 | `saqqez` | <span dir="rtl">بنا بر گزارش‌ها، در خاکسپاری‌اش در سقز، سوگواران «ژن، ژیان، ئازادی» سر دادند؛ شعاری برآمده از جنبش زنان کرد.</span> | According to reports, at her burial in Saqqez, mourners chanted "Jin, Jiyan, Azadî", a slogan that emerged from the Kurdish women's movement. |  |
| B5.1 | `spread` | <span dir="rtl">ترجمهٔ فارسی‌اش، «زن، زندگی، آزادی»، با اعتراضات به دانشگاه‌ها و شهرهای سراسر ایران رسید.</span> | Its Persian translation, "Zan, Zendegi, Azadi" [Woman, Life, Freedom], reached universities and cities across Iran with the protests. |  |
| B5.2 | `spread` | <span dir="rtl">مقام‌ها اعتراضات را «اغتشاشات» و کار دشمنان خارجی خواندند.</span> | The authorities called the protests "riots" and the work of foreign enemies. |  |
| B6.1 | `count` | <span dir="rtl">در آذر ۱۴۰۱، فرمانده‌ای از سپاه گفت بیش از سیصد نفر، از جمله نیروهای امنیتی، جان باخته‌اند.</span> | In Azar 1401 [November 2022], a Revolutionary Guards commander said more than three hundred people, including security forces, had lost their lives. | yes |
| B6.2 | `count` | <span dir="rtl">سازمان غیردولتی حقوق بشر ایران جان‌باختن دست‌کم ۵۵۱ معترض را ثبت کرد؛ هیئت سازمان ملل این رقم را معتبر دانست.</span> | The non-governmental organisation Iran Human Rights recorded the deaths of at least 551 protesters; the UN mission considered this figure credible. | yes |
| B7.1 | `elsewhere` | <span dir="rtl">در شهرهای بسیاری بیرون از ایران نیز تجمع‌های همبستگی برگزار شد.</span> | Solidarity rallies were also held in many cities outside Iran. |  |
| B8.1 | `after` | <span dir="rtl">به گزارش رسانه‌ها، اعتراضات خیابانی به‌تدریج فروکش کرد، اما بسیاری از زنان همچنان بی‌روسری دیده می‌شوند.</span> | According to media reports, street protests gradually subsided, but many women are still seen without a headscarf. |  |
| B8.2 | `after` | <span dir="rtl">مجلس قانون تازهٔ حجاب را تصویب کرد؛ اجرایش از آذر ۱۴۰۳ به تصمیم شورای عالی امنیت ملی متوقف مانده است.</span> | Parliament passed a new hijab law; since Azar 1403 [December 2024] its implementation has been halted by decision of the Supreme National Security Council. |  |
| B8.3 | `after` | <span dir="rtl">حجاب همچنان اجباری است.</span> | Hijab remains compulsory. |  |
| B9.1 | `name` | <span dir="rtl">نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:</span> | The Kurdish inscription on her temporary gravestone, in translation: |  |
| B9.2 | `name` | <span dir="rtl">ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.</span> | Dear Jina, you will not die; your name will become a symbol [ramz: symbol, code]. |  |

**Portrait (P) — 77 words**

| id | beat | Persian (display) | English | death |
|---|---|---|---|---|
| P1 | `jina` | <span dir="rtl">گشت ارشاد مهسا (ژینا) امینی، زن جوانی از سقز، را در تهران در ارتباط با حجابش بازداشت کرد.</span> | The Guidance Patrol detained Mahsa (Jina) Amini, a young woman from Saqqez, in Tehran in connection with her hijab. |  |
| P2 | `jina` | <span dir="rtl">سه روز بعد درگذشت.</span> | Three days later she died. | yes |
| P3 | `accounts` | <span dir="rtl">مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.</span> | Iran's authorities say she was not beaten, and they attribute her death to an underlying illness. |  |
| P4 | `accounts` | <span dir="rtl">خانواده‌اش می‌گویند او سالم بود و کتک خورد.</span> | Her family says she was healthy and was beaten. |  |
| P5 | `accounts` | <span dir="rtl">هیئت حقیقت‌یاب سازمان ملل نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید؛ ایران آن را رد کرد.</span> | The UN fact-finding mission concluded that physical violence in custody led to her death; Iran rejected it. |  |
| P6 | `name` | <span dir="rtl">نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:</span> | The Kurdish inscription on her temporary gravestone, in translation: |  |
| P7 | `name` | <span dir="rtl">ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.</span> | Dear Jina, you will not die; your name will become a symbol. |  |

Measured (§9.2): a full test take of the L narration with `eleven_v4`, one clip per sentence, gave 130.4 s of trimmed speech (about 113 spoken words per minute; about 103 including each clip's own lead-in and tail), so the P narration will run about 40 seconds; the timing lock (§10.3) uses the measured clip lengths, not this estimate. The subtitle cues inside the JSON are broken by phrase (never inside an ezafe, a number and its noun, a name, or a negation) and are never re-wrapped.

Write `build/script_fa.json` as the text inside the fenced block below followed by exactly one newline; `sha256sum` must give `0bc0f7a89a12d00509f486918f06f7e90920dc143961f7a2b37a0df878e36714`. If it differs, the copy is wrong, not the brief.

```json
{
 "version": "1.0",
 "language": "fa",
 "L": [
  {
   "id": "B2.1",
   "beat": "jina",
   "display": "مهسا (ژینا) امینی، زن جوان کردی از سقز بود.",
   "tts": "مهسا ژینا امینی، زن جوان کُردی از سَقِّز بود.",
   "words_display": 9,
   "words_tts": 9,
   "death": false,
   "english": "Mahsa (Jina) Amini was a young Kurdish woman from Saqqez.",
   "sub_fa": [
    [
     "مهسا (ژینا) امینی،",
     "زن جوان کردی از سقز بود."
    ]
   ],
   "sub_en": [
    [
     "Mahsa (Jina) Amini was a young",
     "Kurdish woman from Saqqez."
    ]
   ]
  },
  {
   "id": "B2.2",
   "beat": "jina",
   "display": "۲۲ شهریور ۱۴۰۱، گشت ارشاد او را در تهران، در ارتباط با حجابش، بازداشت کرد.",
   "tts": "بیست‌ودوم شهریور هزار و چهارصد و یک، گشت ارشاد او را در تهران، در ارتباط با حجابش، بازداشت کرد.",
   "words_display": 15,
   "words_tts": 19,
   "death": false,
   "english": "On 22 Shahrivar 1401 [13 September 2022], the Guidance Patrol detained her in Tehran in connection with her hijab.",
   "sub_fa": [
    [
     "۲۲ شهریور ۱۴۰۱، گشت ارشاد",
     "او را در تهران،"
    ],
    [
     "در ارتباط با حجابش، بازداشت کرد."
    ]
   ],
   "sub_en": [
    [
     "On 13 September 2022, in Tehran,",
     "the Guidance Patrol detained her"
    ],
    [
     "in connection with her hijab."
    ]
   ]
  },
  {
   "id": "B2.3",
   "beat": "jina",
   "display": "در مقر پلیس از حال رفت و سه روز بعد در بیمارستان درگذشت.",
   "tts": "در مَقَر پلیس از حال رفت و سه روز بعد در بیمارستان درگذشت.",
   "words_display": 13,
   "words_tts": 13,
   "death": true,
   "english": "She collapsed at the police facility and died in hospital three days later.",
   "sub_fa": [
    [
     "در مقر پلیس از حال رفت",
     "و سه روز بعد در بیمارستان درگذشت."
    ]
   ],
   "sub_en": [
    [
     "She collapsed at the police facility",
     "and died in hospital three days later."
    ]
   ]
  },
  {
   "id": "B3.1",
   "beat": "accounts",
   "display": "مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.",
   "tts": "مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.",
   "words_display": 14,
   "words_tts": 14,
   "death": false,
   "english": "Iran's authorities say she was not beaten, and they attribute her death to an underlying illness.",
   "sub_fa": [
    [
     "مقام‌های ایران می‌گویند",
     "او کتک نخورد"
    ],
    [
     "و مرگش را به بیماری‌ای",
     "زمینه‌ای نسبت می‌دهند."
    ]
   ],
   "sub_en": [
    [
     "Iran's authorities say she was not beaten,"
    ],
    [
     "and attribute her death",
     "to an underlying illness."
    ]
   ]
  },
  {
   "id": "B3.2",
   "beat": "accounts",
   "display": "خانواده‌اش می‌گویند او سالم بود و کتک خورد.",
   "tts": "خانواده‌اش می‌گویند او سالم بود و کتک خورد.",
   "words_display": 8,
   "words_tts": 8,
   "death": false,
   "english": "Her family says she was healthy and was beaten.",
   "sub_fa": [
    [
     "خانواده‌اش می‌گویند",
     "او سالم بود و کتک خورد."
    ]
   ],
   "sub_en": [
    [
     "Her family says she was healthy",
     "and was beaten."
    ]
   ]
  },
  {
   "id": "B3.3",
   "beat": "accounts",
   "display": "هیئت حقیقت‌یاب سازمان ملل در اسفند ۱۴۰۲ نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید.",
   "tts": "هیئت حقیقت‌یاب سازمان ملل در اسفند هزار و چهارصد و دو نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید.",
   "words_display": 16,
   "words_tts": 20,
   "death": false,
   "english": "In Esfand 1402 [March 2024], the UN fact-finding mission concluded that physical violence in custody led to her death.",
   "sub_fa": [
    [
     "هیئت حقیقت‌یاب سازمان ملل",
     "در اسفند ۱۴۰۲ نتیجه گرفت"
    ],
    [
     "خشونت فیزیکی در بازداشت",
     "به مرگش انجامید."
    ]
   ],
   "sub_en": [
    [
     "In March 2024, the UN fact-finding mission",
     "concluded that physical violence"
    ],
    [
     "in custody led to her death."
    ]
   ]
  },
  {
   "id": "B3.4",
   "beat": "accounts",
   "display": "ایران آن را رد کرد.",
   "tts": "ایران آن را رد کرد.",
   "words_display": 5,
   "words_tts": 5,
   "death": false,
   "english": "Iran rejected it.",
   "sub_fa": [
    [
     "ایران آن را رد کرد."
    ]
   ],
   "sub_en": [
    [
     "Iran rejected it."
    ]
   ]
  },
  {
   "id": "B4.1",
   "beat": "saqqez",
   "display": "بنا بر گزارش‌ها، در خاکسپاری‌اش در سقز، سوگواران «ژن، ژیان، ئازادی» سر دادند؛ شعاری برآمده از جنبش زنان کرد.",
   "tts": "بنا بر گزارش‌ها، در خاکسپاری‌اش در سَقِّز، سوگواران «ژِن، ژیان، ئازادی» سر دادند؛ شعاری برآمده از جنبش زنان کُرد.",
   "words_display": 19,
   "words_tts": 19,
   "death": false,
   "english": "According to reports, at her burial in Saqqez, mourners chanted \"Jin, Jiyan, Azadî\", a slogan that emerged from the Kurdish women's movement.",
   "sub_fa": [
    [
     "بنا بر گزارش‌ها،",
     "در خاکسپاری‌اش در سقز،"
    ],
    [
     "سوگواران «ژن، ژیان، ئازادی» سر دادند؛",
     "شعاری برآمده از جنبش زنان کرد."
    ]
   ],
   "sub_en": [
    [
     "According to reports, at her burial",
     "in Saqqez, mourners chanted"
    ],
    [
     "\"Jin, Jiyan, Azadî\", a slogan that emerged",
     "from the Kurdish women's movement."
    ]
   ]
  },
  {
   "id": "B5.1",
   "beat": "spread",
   "display": "ترجمهٔ فارسی‌اش، «زن، زندگی، آزادی»، با اعتراضات به دانشگاه‌ها و شهرهای سراسر ایران رسید.",
   "tts": "ترجمهٔ فارسی‌اش، «زن، زندگی، آزادی»، با اعتراضات به دانشگاه‌ها و شهرهای سراسر ایران رسید.",
   "words_display": 14,
   "words_tts": 14,
   "death": false,
   "english": "Its Persian translation, \"Zan, Zendegi, Azadi\" [Woman, Life, Freedom], reached universities and cities across Iran with the protests.",
   "sub_fa": [
    [
     "ترجمهٔ فارسی‌اش،",
     "«زن، زندگی، آزادی»،"
    ],
    [
     "با اعتراضات به دانشگاه‌ها",
     "و شهرهای سراسر ایران رسید."
    ]
   ],
   "sub_en": [
    [
     "Its Persian translation,",
     "\"Woman, Life, Freedom\","
    ],
    [
     "reached universities and cities",
     "across Iran with the protests."
    ]
   ]
  },
  {
   "id": "B5.2",
   "beat": "spread",
   "display": "مقام‌ها اعتراضات را «اغتشاشات» و کار دشمنان خارجی خواندند.",
   "tts": "مقام‌ها اعتراضات را «اغتشاشات» و کار دشمنان خارجی خواندند.",
   "words_display": 9,
   "words_tts": 9,
   "death": false,
   "english": "The authorities called the protests \"riots\" and the work of foreign enemies.",
   "sub_fa": [
    [
     "مقام‌ها اعتراضات را «اغتشاشات»",
     "و کار دشمنان خارجی خواندند."
    ]
   ],
   "sub_en": [
    [
     "The authorities called the protests",
     "\"riots\" and the work of foreign enemies."
    ]
   ]
  },
  {
   "id": "B6.1",
   "beat": "count",
   "display": "در آذر ۱۴۰۱، فرمانده‌ای از سپاه گفت بیش از سیصد نفر، از جمله نیروهای امنیتی، جان باخته‌اند.",
   "tts": "در آذر هزار و چهارصد و یک، فرمانده‌ای از سپاه گفت بیش از سیصد نفر، از جمله نیروهای امنیتی، جان باخته‌اند.",
   "words_display": 17,
   "words_tts": 21,
   "death": true,
   "english": "In Azar 1401 [November 2022], a Revolutionary Guards commander said more than three hundred people, including security forces, had lost their lives.",
   "sub_fa": [
    [
     "در آذر ۱۴۰۱، فرمانده‌ای از سپاه گفت",
     "بیش از سیصد نفر،"
    ],
    [
     "از جمله نیروهای امنیتی،",
     "جان باخته‌اند."
    ]
   ],
   "sub_en": [
    [
     "In November 2022, a Revolutionary Guards",
     "commander said more than 300 people,"
    ],
    [
     "including security forces,",
     "had lost their lives."
    ]
   ]
  },
  {
   "id": "B6.2",
   "beat": "count",
   "display": "سازمان غیردولتی حقوق بشر ایران جان‌باختن دست‌کم ۵۵۱ معترض را ثبت کرد؛ هیئت سازمان ملل این رقم را معتبر دانست.",
   "tts": "سازمان غیردولتی حقوق بشر ایران جان‌باختن دست‌کم پانصد و پنجاه و یک معترض را ثبت کرد؛ هیئت سازمان ملل این رقم را معتبر دانست.",
   "words_display": 20,
   "words_tts": 24,
   "death": true,
   "english": "The non-governmental organisation Iran Human Rights recorded the deaths of at least 551 protesters; the UN mission considered this figure credible.",
   "sub_fa": [
    [
     "سازمان غیردولتی حقوق بشر ایران",
     "جان‌باختن دست‌کم ۵۵۱ معترض را"
    ],
    [
     "ثبت کرد؛ هیئت سازمان ملل",
     "این رقم را معتبر دانست."
    ]
   ],
   "sub_en": [
    [
     "The NGO Iran Human Rights recorded",
     "the deaths of at least 551 protesters."
    ],
    [
     "The UN mission considered",
     "this figure credible."
    ]
   ]
  },
  {
   "id": "B7.1",
   "beat": "elsewhere",
   "display": "در شهرهای بسیاری بیرون از ایران نیز تجمع‌های همبستگی برگزار شد.",
   "tts": "در شهرهای بسیاری بیرون از ایران نیز تجمع‌های همبستگی برگزار شد.",
   "words_display": 11,
   "words_tts": 11,
   "death": false,
   "english": "Solidarity rallies were also held in many cities outside Iran.",
   "sub_fa": [
    [
     "در شهرهای بسیاری بیرون از ایران",
     "نیز تجمع‌های همبستگی برگزار شد."
    ]
   ],
   "sub_en": [
    [
     "Solidarity rallies were also held",
     "in many cities outside Iran."
    ]
   ]
  },
  {
   "id": "B8.1",
   "beat": "after",
   "display": "به گزارش رسانه‌ها، اعتراضات خیابانی به‌تدریج فروکش کرد، اما بسیاری از زنان همچنان بی‌روسری دیده می‌شوند.",
   "tts": "به گزارش رسانه‌ها، اعتراضات خیابانی به‌تدریج فروکش کرد، اما بسیاری از زنان همچنان بی‌روسری دیده می‌شوند.",
   "words_display": 16,
   "words_tts": 16,
   "death": false,
   "english": "According to media reports, street protests gradually subsided, but many women are still seen without a headscarf.",
   "sub_fa": [
    [
     "به گزارش رسانه‌ها، اعتراضات خیابانی",
     "به‌تدریج فروکش کرد،"
    ],
    [
     "اما بسیاری از زنان همچنان",
     "بی‌روسری دیده می‌شوند."
    ]
   ],
   "sub_en": [
    [
     "According to media reports,",
     "street protests gradually subsided,"
    ],
    [
     "but many women are still seen",
     "without a headscarf."
    ]
   ]
  },
  {
   "id": "B8.2",
   "beat": "after",
   "display": "مجلس قانون تازهٔ حجاب را تصویب کرد؛ اجرایش از آذر ۱۴۰۳ به تصمیم شورای عالی امنیت ملی متوقف مانده است.",
   "tts": "مجلس قانون تازهٔ حجاب را تصویب کرد؛ اجرایش از آذر هزار و چهارصد و سه به تصمیم شورای عالی امنیت ملی متوقف مانده است.",
   "words_display": 20,
   "words_tts": 24,
   "death": false,
   "english": "Parliament passed a new hijab law; since Azar 1403 [December 2024] its implementation has been halted by decision of the Supreme National Security Council.",
   "sub_fa": [
    [
     "مجلس قانون تازهٔ حجاب را تصویب کرد؛",
     "اجرایش از آذر ۱۴۰۳"
    ],
    [
     "به تصمیم شورای عالی امنیت ملی",
     "متوقف مانده است."
    ]
   ],
   "sub_en": [
    [
     "Parliament passed a new hijab law.",
     "Since December 2024, its implementation"
    ],
    [
     "has been halted by decision of",
     "the Supreme National Security Council."
    ]
   ]
  },
  {
   "id": "B8.3",
   "beat": "after",
   "display": "حجاب همچنان اجباری است.",
   "tts": "حجاب همچنان اجباری است.",
   "words_display": 4,
   "words_tts": 4,
   "death": false,
   "english": "Hijab remains compulsory.",
   "sub_fa": [
    [
     "حجاب همچنان اجباری است."
    ]
   ],
   "sub_en": [
    [
     "Hijab remains compulsory."
    ]
   ]
  },
  {
   "id": "B9.1",
   "beat": "name",
   "display": "نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:",
   "tts": "نوشتهٔ کُردی سنگ موقت مزارش، در ترجمه:",
   "words_display": 7,
   "words_tts": 7,
   "death": false,
   "english": "The Kurdish inscription on her temporary gravestone, in translation:",
   "sub_fa": [
    [
     "نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:"
    ]
   ],
   "sub_en": [
    [
     "The Kurdish inscription on her",
     "temporary gravestone, in translation:"
    ]
   ]
  },
  {
   "id": "B9.2",
   "beat": "name",
   "display": "ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.",
   "tts": "ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.",
   "words_display": 8,
   "words_tts": 8,
   "death": false,
   "english": "Dear Jina, you will not die; your name will become a symbol [ramz: symbol, code].",
   "sub_fa": [
    [
     "ژینا جان تو نمی‌میری،",
     "نامت یک رمز می‌شود."
    ]
   ],
   "sub_en": [
    [
     "\"Dear Jina, you will not die,"
    ],
    [
     "your name will become a symbol.\""
    ]
   ]
  }
 ],
 "P": [
  {
   "id": "P1",
   "beat": "jina",
   "display": "گشت ارشاد مهسا (ژینا) امینی، زن جوانی از سقز، را در تهران در ارتباط با حجابش بازداشت کرد.",
   "tts": "گشت ارشاد مهسا ژینا امینی، زن جوانی از سَقِّز، را در تهران در ارتباط با حجابش بازداشت کرد.",
   "words_display": 18,
   "words_tts": 18,
   "death": false,
   "english": "The Guidance Patrol detained Mahsa (Jina) Amini, a young woman from Saqqez, in Tehran in connection with her hijab.",
   "sub_fa": [
    [
     "گشت ارشاد مهسا (ژینا) امینی،",
     "زن جوانی از سقز، را در تهران"
    ],
    [
     "در ارتباط با حجابش بازداشت کرد."
    ]
   ],
   "sub_en": [
    [
     "The Guidance Patrol detained",
     "Mahsa (Jina) Amini, a young woman"
    ],
    [
     "from Saqqez, in Tehran,",
     "in connection with her hijab."
    ]
   ]
  },
  {
   "id": "P2",
   "beat": "jina",
   "display": "سه روز بعد درگذشت.",
   "tts": "سه روز بعد درگذشت.",
   "words_display": 4,
   "words_tts": 4,
   "death": true,
   "english": "Three days later she died.",
   "sub_fa": [
    [
     "سه روز بعد درگذشت."
    ]
   ],
   "sub_en": [
    [
     "Three days later she died."
    ]
   ]
  },
  {
   "id": "P3",
   "beat": "accounts",
   "display": "مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.",
   "tts": "مقام‌های ایران می‌گویند او کتک نخورد و مرگش را به بیماری‌ای زمینه‌ای نسبت می‌دهند.",
   "words_display": 14,
   "words_tts": 14,
   "death": false,
   "english": "Iran's authorities say she was not beaten, and they attribute her death to an underlying illness.",
   "sub_fa": [
    [
     "مقام‌های ایران می‌گویند",
     "او کتک نخورد"
    ],
    [
     "و مرگش را به بیماری‌ای",
     "زمینه‌ای نسبت می‌دهند."
    ]
   ],
   "sub_en": [
    [
     "Iran's authorities say she was not beaten,"
    ],
    [
     "and attribute her death",
     "to an underlying illness."
    ]
   ]
  },
  {
   "id": "P4",
   "beat": "accounts",
   "display": "خانواده‌اش می‌گویند او سالم بود و کتک خورد.",
   "tts": "خانواده‌اش می‌گویند او سالم بود و کتک خورد.",
   "words_display": 8,
   "words_tts": 8,
   "death": false,
   "english": "Her family says she was healthy and was beaten.",
   "sub_fa": [
    [
     "خانواده‌اش می‌گویند",
     "او سالم بود و کتک خورد."
    ]
   ],
   "sub_en": [
    [
     "Her family says she was healthy",
     "and was beaten."
    ]
   ]
  },
  {
   "id": "P5",
   "beat": "accounts",
   "display": "هیئت حقیقت‌یاب سازمان ملل نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید؛ ایران آن را رد کرد.",
   "tts": "هیئت حقیقت‌یاب سازمان ملل نتیجه گرفت خشونت فیزیکی در بازداشت به مرگش انجامید؛ ایران آن را رد کرد.",
   "words_display": 18,
   "words_tts": 18,
   "death": false,
   "english": "The UN fact-finding mission concluded that physical violence in custody led to her death; Iran rejected it.",
   "sub_fa": [
    [
     "هیئت حقیقت‌یاب سازمان ملل نتیجه گرفت",
     "خشونت فیزیکی در بازداشت"
    ],
    [
     "به مرگش انجامید؛",
     "ایران آن را رد کرد."
    ]
   ],
   "sub_en": [
    [
     "The UN fact-finding mission concluded",
     "that physical violence in custody"
    ],
    [
     "led to her death. Iran rejected it."
    ]
   ]
  },
  {
   "id": "P6",
   "beat": "name",
   "display": "نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:",
   "tts": "نوشتهٔ کُردی سنگ موقت مزارش، در ترجمه:",
   "words_display": 7,
   "words_tts": 7,
   "death": false,
   "english": "The Kurdish inscription on her temporary gravestone, in translation:",
   "sub_fa": [
    [
     "نوشتهٔ کردی سنگ موقت مزارش، در ترجمه:"
    ]
   ],
   "sub_en": [
    [
     "The Kurdish inscription on her",
     "temporary gravestone, in translation:"
    ]
   ]
  },
  {
   "id": "P7",
   "beat": "name",
   "display": "ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.",
   "tts": "ژینا جان تو نمی‌میری، نامت یک رمز می‌شود.",
   "words_display": 8,
   "words_tts": 8,
   "death": false,
   "english": "Dear Jina, you will not die; your name will become a symbol.",
   "sub_fa": [
    [
     "ژینا جان تو نمی‌میری،",
     "نامت یک رمز می‌شود."
    ]
   ],
   "sub_en": [
    [
     "\"Dear Jina, you will not die,"
    ],
    [
     "your name will become a symbol.\""
    ]
   ]
  }
 ],
 "optional_cut_order_L": [
  {
   "step": 1,
   "action": "replace B4.1 with B4.1-alt",
   "B4.1-alt": {
    "display": "بنا بر گزارش‌ها، در خاکسپاری‌اش در سقز، سوگواران شعاری کردی سر دادند، برآمده از جنبش زنان کرد.",
    "tts": "بنا بر گزارش‌ها، در خاکسپاری‌اش در سَقِّز، سوگواران شعاری کُردی سر دادند، برآمده از جنبش زنان کُرد.",
    "sub_fa": [
     [
      "بنا بر گزارش‌ها،",
      "در خاکسپاری‌اش در سقز،"
     ],
     [
      "سوگواران شعاری کردی سر دادند،",
      "برآمده از جنبش زنان کرد."
     ]
    ],
    "sub_en": [
     [
      "According to reports, at her burial",
      "in Saqqez, mourners chanted"
     ],
     [
      "a Kurdish slogan that emerged",
      "from the Kurdish women's movement."
     ]
    ]
   }
  },
  {
   "step": 2,
   "action": "drop B7.1"
  },
  {
   "step": 3,
   "action": "in B5.1 drop the words «دانشگاه‌ها و»; its second Persian cue becomes [\"با اعتراضات به شهرهای\", \"سراسر ایران رسید.\"] and its second English cue [\"reached cities across Iran\", \"with the protests.\"]"
  }
 ],
 "never_cut": [
  "B3.1",
  "B3.2",
  "B3.3",
  "B3.4",
  "B8.1 without B8.3",
  "B8.3 without B8.1"
 ]
}
```

### 7.3 The works (fixed list, fixed rules; the drawing is designed)

Each work is redrawn from your reading sheet (§6.1). "Must stay recognisable" names what a viewer who knows the source must find within one second; everything else — light, palette, the moment of day, framing for 16:9 and 9:16, how much of the scene is built around it — is designed. The reference photographs are in `reference/woman-life-freedom/references/` (open the 2400-pixel copies in `references/view/`; the originals are kept for the record), each original with a `.json` licence record.

| id | Work | Reference | Must stay recognisable | Rules | Credit (verbatim) |
|---|---|---|---|---|---|
| W1 | The epitaph, handwritten | 05 (handwriting only) | Blue marker strokes, hatched letterforms, a white card against a pale sky | Text is T1 (the stone's wording, never the sign's variant). No crowd, no hashtag. | Handwriting after a sign photographed by Pirehelokan, Richmond Hill, Ontario, 1 Oct 2022 — CC BY-SA 4.0 |
| W2 | The grave and her portrait behind glass | 03 | The marble frame, the glass, the green calligraphy «مهسا», plants and flowers | Her portrait is seen through the glass with reflections drifting over it (§6.7.2). No dates, no small text, no child's hands. | Photo: Darafsh, Aichi cemetery, Saqqez, 2023 — CC BY-SA 4.0 |
| W3 | The book-shaped headstone | 04 | The open-book stone, the green «ژینا», the floral ornament, a pink flower | The two carved lines above the name are a verse, not the epitaph: draw them illegible. | Photo: Darafsh, Aichi cemetery, Saqqez, 2023 — CC BY-SA 4.0 |
| W4 | The slogan in square Kufic | 12 (the idea of the grid only) | A square-Kufic block of «زن زندگی آزادی» | Your own setting, built by the rules of square Kufic (banna'i) — never a copy of reference 12, whose designer is unverified. Its colours are yours; never flag colours. | Square-Kufic setting of «زن زندگی آزادی» drawn for this film |
| W5 | Keshavarz Boulevard, Tehran, 20 Sep 2022 | 01, 02 | A woman seen from behind — brown-grey hair, backpack straps — looking down a tunnel of plane trees in low warm light | No gas, smoke or haze that reads as tear gas; no running figures; every other figure is a distant, still silhouette in the same light and language (§6.7.4); no thrown objects. Draw no detail of the woman beyond hair and backpack straps. | Photos: Darafsh, Tehran, 20 Sep 2022 — CC BY-SA 4.0 |
| W6 | Amir Kabir University courtyard, 20 Sep 2022 (optional) | 11 | Trees, the yellow building, a dense gathering seen from far | No faces at all. First rung of the scope ladder if time is short. | Photo: Darafsh, Tehran, 20 Sep 2022 — CC BY-SA 4.0 |
| W7 | A lock of cut hair held up to the sky | 06 | Low angle, an arm at full stretch, the dark lock against a pale sky, scissors in the lowered hand | The woman is a silhouette or seen from below with no features; the second woman is removed. Hair-cutting is a traditional mourning rite (*gisuboran*). | Photo: Matt Hrkac, Melbourne, 24 Sep 2022 — CC BY 2.0 |
| W8 | The red fountains of Tehran, Oct 2022 | none (from description) | A park fountain at night, its basin filled with opaque deep-red water; trees reflected | Drawn from the written description only (anonymous art action, about 7 Oct 2022, reported by AFP and VOA). Still water, no splashing, deep maroon. Shown in beat 5, voice-free, never in beat 6 or near a death sentence; already red as the action left it, entered by a transition — never red flowing, spreading or filling on screen (§6.8). | After an anonymous art action, Tehran, October 2022 |
| W9 | The vigil, Piccadilly Circus, London, 21 Sep 2022 | 16 | A row of people holding sheets with her portrait, repeated; the dark fountain plinth | No legible placard text; faces featureless; the portraits small (§6.7.2). | Photo: Garry Knight, London, 21 Sep 2022 — CC0 |
| W10 | The Berlin rally, 22 Oct 2022 | 07, 08, 09, 17 | A long red banner FRAU · LEBEN · FREIHEIT over a vast crowd under autumn trees; or the trilingual cloth banner | Only T5 is legible; every flag, placard and portrait of a political figure illegible. | Photos: Leonhard Lenz (CC0) and Ilias Bartolini (CC BY-SA 2.0), Berlin, 22 Oct 2022 |
| W11 | The Frankfurt mural | 14 | A greyscale spray portrait, gaze to the left; the block letters JIN / JIYAN / AZADÎ with heavy shadow; a wall marked for demolition | Her face per §6.7.2; the small flag omitted. | Mural: unknown artist; photo: Ostendfaxpost, Frankfurt, 2024 — CC BY 4.0 |
| W12 | The Berlin-Friedrichshain mural | 15 | Her portrait in white engraved lines on teal; a band of flowers with the word Freiheit; shrubs in front | Her face per §6.7.2. | Mural: unknown artist; photo: Singlespeedfahrer, Berlin, 2025 — CC0 |

Credits-gallery strings (T10): Persian «بازآفرینی به سبک پیکسل‌آرت. همهٔ فریم‌ها با کد ساخته شده‌اند.»; English *"Redrawn as pixel art. Every frame computed."*; licence line *"This film: CC BY-SA 4.0"*.

**Not in this film, and why** (do not add them): the photograph of her in a hospital bed (dignity); the photograph of her relatives embracing in hospital (private grief; rights reserved); the schoolgirls' gesture at leaders' portraits (minors; partisan staging); the cartoon-character mural (a studio-owned character); a magazine cover, and named living artists' posters and works (rights reserved; redrawing them is copying them); the image of a detained man tied to a flagpole (humiliation); the hacked broadcast and cartoons of leaders (incitement imagery); the ponytail video and the 2017 "girl on the utility box" (misattributed or misdated); the woman photographed in her underwear (a private person); the song "Baraye" and every other song (rights reserved; §9.1); the 40th-day photograph of the woman standing on a car (rights reserved; not to be evoked).

### 7.4 Creative brief (designed)

**The heart.** A young woman's death in custody, whose cause is still disputed, and how her private name became a public sign. Her temporary gravestone said, in Kurdish, that her name would become a *remz* — a symbol, a code. The film shows where that name has since been written: on a stone, on a card held up at a rally, in a lock of hair, in lettering, on walls in other countries. The human presences are the ones the works hold: a card held up, a lock of hair, a crowd seen as light.

**The images that must land.**
1. **The hair becomes her name** (beat 7, after B7.1 — the photograph was taken at a rally in Melbourne, so it belongs with the rallies outside Iran). The cut lock against the pale sky; the wind lifts it; its strands — simulated, not morphed — settle into «ژینا» in the same hand that writes the epitaph (W1). The film's single reserved accent belongs to her hair and her name — first fully spent in this moment.
2. **The last word** (beat 9). The epitaph that opened the film unfinished is completed: «ڕەمز» is written last, at first light, and held.

**What the facts require of the picture.** Places, not events: the evening street, a closed door, a lit window — never the arrest, the van, the hospital. Equal pictures for equal accounts in beat 3. The count spoken over a dry basin at night, and the basin stays dry; the red fountains belong to beat 5, far from any number. Her face only inside the works that already hold it. Crowds as forms of light and colour, never as faces.

**Sparks from the art panel** (optional; your own are welcome — the panel's favoured treatment, discussed in two rounds, is offered here as a starting point, not a rule):
- *The unfinished sentence.* The cold open writes the epitaph stroke by stroke — and stops before «ڕەمز». The gap stays open for the whole film and is closed only at the end.
- *One line.* A single one-pixel stroke draws the epitaph, becomes a hair, a contour, the vanishing line of a boulevard, a banner's edge, an engraved line on a wall — carrying the eye between works. Drawn in full only three times (the epitaph, hair into name, the last word); elsewhere a brief lead or a contour handed over.
- *One day.* A light clock built from the facts: evening (the arrest), night (the hospital, the count), morning (the burial), low sun (the boulevard), daylight (Berlin), dusk (after), first light (the last word).
- *Lit diorama, engraved hair.* Worlds and people as lit 2.5-D pixel dioramas; hair alone drawn in engraved one-pixel line clusters with a warm thread-gold rim — the one accent, used only on hair and on her name, ending as gold light on the green «ژینا» of the stone.
- *After the death, stillness.* B2.3 is spoken over the lit window, unchanged. Only after the sentence ends, in beat 2's voice-free span, the window's light steps down through its palette to near-darkness, and 2–3 s of room tone follow (a declared stillness, §12.3 C03). The line is never broken. If a hard cut is used here, it falls inside that silence, from darkness into the place of beat 3, where the single line returns alone for the three accounts; it becomes many lines only at Saqqez (beat 4).
- *Hands, not faces.* Only the hands the works contain: the raised hand with the lock and the lowered hand with the scissors (W7), the hands holding the portrait sheets (W9). The epitaph is written by the line itself, with no hand.
- *The boulevard returns.* Keshavarz Boulevard in the identical frame at dusk in beat 8, the film's only reprise — empty, or with a few distant passers-by of at most 8 art pixels, of mixed dress, heads not legible at that scale; no figure singled out, none staged walking away. The narration of beat 8 is spoken here; the murals W11 and W12 follow after its last sentence, in silence.
- *Kufic as the turn.* At Saqqez, one line becomes many and falls into the square-Kufic grid, word by word — one, then two, then three — the only time the slogan is drawn whole.

**The turn.** From one line to many — from a private name to a shared sign — at Saqqez (beat 4).

**The ending.** Quiet and open. The last word is written; the light holds; nothing resolves into triumph. Then the gallery.

### 7.5 Truth checks before any master is rendered (gate H01)

Implement as `tools/qa/truth.*`, one command, exit code 0 required:
1. `build/script_fa.json` equals §7.2's JSON byte for byte (sha256 in §7.2).
2. Every voice clip's transcription (§10.3) matches its sentence after the normalization of §9.2 with a character error rate ≤ 5 %, every proper noun of the sentence present (مهسا، ژینا، امینی، سقز، کردستان، تهران، ارشاد، ایران، سازمان ملل، سپاه، حقوق بشر), and detected language Persian; every clip with an error above 0 is listed, with both texts, in `owner_listening_sheet.md`.
3. `build/strings.json` equals §6.4's table; every drawn string id used in `look.json` exists in it.
4. The cue sheet satisfies §6.5 (gate E01–E03) and the picture lengths lie in §6.2's ranges.
5. No file of the reference pack is referenced by any path, URL or import in `src/`, `tools/` or `audio/` (gate F01).

---

## 8. Beat sheets

The order, works, duration ranges, voice-free minimums and narration of each beat are fixed; the timecodes are computed at the timing lock (§10.3) and written to `build/timeline.json` as `{format, fps: 60, frames, beats: [{id, t0, t1, f0, f1, sentences: [{id, t0, t1}], voiceFree: [{t0, t1}]}], gallery: {t0, t1}}`. What the picture shows inside a beat — shots, transitions, light, the moment a work appears — is designed and recorded in `build/look.json`.

### 8.1 Landscape (L) — picture 195–215 s, then the 20.000 s gallery

| beat | id | duration | works (§7.3) | narration (§7.2) | voice-free minimum (one unbroken span) |
|---|---|---|---|---|---|
| 1 | `open` | 12–16 s | W1, written without «ڕەمز» if the design follows the spark | none | the whole beat |
| 2 | `jina` | 22–30 s | places only: an evening street, a closed door, a lit window | B2.1–B2.3 | 3 s, ending the beat |
| 3 | `accounts` | 26–34 s | one place, three equal states (§6.8) | B3.1–B3.4 | 2 s |
| 4 | `saqqez` | 20–28 s | W2, W3, W4 (the turn) | B4.1 | 6 s (the slogan is drawn) |
| 5 | `spread` | 22–30 s | W8 (first, voice-free, at least 3 s), W5, W6 (optional) | B5.1, B5.2 | 5 s |
| 6 | `count` | 28–36 s | a dry park basin at night, still trees; no red | B6.1, B6.2 | 6 s (the still basin, after the voice) |
| 7 | `elsewhere` | 24–32 s | W9, W10, then W7 → «ژینا» | B7.1 | 8 s, after B7.1, of which at least 4 s on the hair becoming the name |
| 8 | `after` | 28–36 s | the boulevard at dusk (B8 spoken here), then W11, W12 | B8.1–B8.3 | 8 s, on the murals, after the last sentence |
| 9 | `name` | 16–22 s | W1 completed: «ڕەمز» written last | B9.1, B9.2 | 8 s, the final hold |
| — | `gallery` | 20.000 s | every work, small, with its credit (§6.9) | none | whole |

The sum of the beats must lie within 195–215 s (the ranges are deliberately loose; the total is the constraint). Estimate from a full test take of this narration (18 clips, trimmed speech 130.4 s): about 130 s of voice, 58 s of voice-free minimums, about 9 s of image pre-rolls and 6 s of sentence gaps — near 203 s. The measured share of the picture without voice must reach 30 % (it will usually land near 40 %).

### 8.2 Portrait (P) — picture 80–95 s, then the 8.000 s credits card

| beat | id | duration | works | narration (§7.2, P) | voice-free minimum |
|---|---|---|---|---|---|
| 1 | `open` | 6–8 s | W1 (unfinished) | none | whole beat |
| 2 | `jina` | 12–16 s | a place | P1, P2 | 1.5 s |
| 3 | `accounts` | 20–26 s | one place, three equal states | P3, P4, P5 | 1.5 s |
| 4 | `saqqez` | 10–14 s | W2 or W3, W4 | none | whole beat |
| 5 | `spread` | 10–14 s | W5 | none | whole beat |
| 6 | `elsewhere` | 10–14 s | W10 or W12, then W7 → «ژینا» | none | whole beat |
| 7 | `name` | 12–16 s | W1 completed | P6, P7 | 5 s, the final hold |
| — | `credits` | 8.000 s | credits card | none | whole |

The sum of the P beats must lie within 80–95 s.

### 8.3 Joins and the end

- The gallery is entered by a designed transition from the final hold, never a cut to black first; it ends on a held frame for at least 2 s; the audio fades to silence over the last 1.5 s.
- The film may begin from darkness (the first stroke of the epitaph on a dark ground) — there is no cold-open requirement in this film other than beat 1's silence.

### 8.4 Poster frame

The poster frame is designed: the image that must land (§7.4) at its most beautiful, one per format, recorded in `look.json` as `{format, frame}` and exported as §6.10 states.

---

## 9. Sound

The film must be fully understood with the sound off (through the `_fa` and `_en` versions), and with the sound on it should feel twice as present. The sound is quiet: a Persian voice, designed air, and very little music. All final audio is 48 kHz stereo, exactly as long as its video, normalized with two-pass `loudnorm` to I = −16 LUFS, LRA ≤ 12 and a true-peak target of −2.0 dBTP so the deliverable stays at or below −1.0 dBTP after AAC encoding (Appendix A.6).

### 9.1 Fixed rules

- **No existing music** — no recording, melody, quotation, pastiche or lyric of any song ("Baraye", anthems, folk songs, protest songs). **No crowd or chant recordings**, real or synthesised; no invented voices other than the narrator. **No sound of violence**: no gunfire, explosions, sirens, screams, impacts, tear-gas canisters.
- **All music and ambience are synthesised in this run** from code (physical models, additive or subtractive synthesis, noise shaping, computed convolution rooms), seeded with `20260928` through `mulberry32`. No sample files. The only generated audio from the voice service is the narration.
- **Silence under death and dispute.** Music is absent under every sentence marked `death: true` in §7.2 and throughout beat 3; only the voice and room tone remain (gate G05).
- **Restraint.** Music sounds in at most 35 % of the film's running time; no struck percussion pattern, no march-like pulse; no rise to a climax at the end — the last 20 s of the picture are not the loudest 20 s of the film (gate G06).
- **The epitaph is never spoken in Kurdish by the synthetic voice.** The narrator speaks only its Persian translation, introduced as a translation (§7.2).

### 9.2 The voice (fixed procedure; the choice of voice is designed)

- **Service and model.** The voice service of §5 item 6, model `eleven_v4` with `language_code: "fa"`; if it fails twice, `eleven_v3`; record which. Verified on this machine (2026-10-02): `eleven_v4` reads Persian from the shared Persian voices, a seven-sentence calibration paragraph of 87 spoken words took 43.2 s (about 121 words per minute including natural sentence pauses of about 0.6 s), and its transcription by the service's speech-to-text model `scribe_v2` (`language_code: "fa"`) returned the text word for word with language `fas` at probability 1.0. The `speed` setting had no effect on `eleven_v4` in that test: pacing comes from the per-sentence placement, not from the voice. A full test take of the L narration, one clip per sentence with `previous_text`/`next_text` and seed `20260928`, gave 130.4 s of trimmed speech for 245 spoken words.
- **One clip per sentence.** Generate each sentence of §7.2 separately from its **TTS text** column (numbers as words, ZWNJ, homograph diacritics), passing `previous_text` and `next_text` for continuity; stability high (about 0.7 on `eleven_v4`; "Robust" / 1.0 on `eleven_v3`), style 0, similarity about 0.75, speaker boost on, no emotion tags, a fixed `seed` (`20260928`) for every clip. Convert each to 48 kHz WAV in `audio/voice/<sentence_id>.wav`, trimmed to its first and last sample above −50 dBFS with 10 ms fades.
- **Eligible voices.** Shared voices returned by `GET /v1/shared-voices?language=fa` whose category is `generated` (designed voices, not clones of a person) or premade voices that speak Persian natively. On 2026-10-02 the list held seven: Hooman, Kourosh, Farideh, Setareh, Niloofar, Kaveh, Roya (`ndcUYGFbbd96WXiZVVaQ`, described as an even, measured Tehrani narrator). The film's casting: a calm, unhurried adult voice in standard Tehrani pronunciation and a formal reading register, not performing grief — a woman's voice is preferred (the film is about women, and a younger voice risks sounding like the subject herself). Generate the calibration paragraph (sentences B2.1–B3.4) in at least three eligible voices and choose by measurement and by the panel's reading of the measurements: transcription error, proper nouns, rate (target 105–130 words per minute including pauses), pitch movement (no flat robot, no sing-song; statements fall at the end), clicks or metallic artefacts in the spectrogram. Record the candidates, measurements and choice in `decisions.md`.
- **Verification of every clip** (§7.5 item 2): transcribe each clip with `scribe_v2` and compare on a skeleton of both texts: NFC; Persian ی/ک (fold ي ك ئ); ۀ and the hamza mark folded to ه; ZWNJ, spaces, diacritics and punctuation removed; numbers compared in both forms (the sentence's display digits and its TTS number words — the transcription writes digits, sometimes mixed with words, e.g. «بیست و دوم شهریور 1401»), taking the closer. Compute the character error rate and record it per clip in `audio/voice/stt/<id>.json`. Measured on a full test take of the L narration (2026-10-02): 11 of 18 sentences at 0.000; the rest between 0.015 and 0.058, all orthographic variants (spacing, colloquial spellings such as «خانواده‌ش», ئازادی written آزادی) except one: B5.2 came back as «خوانده‌اند» for «خواندند» (0.043) — exactly the kind of difference the listening sheet must show the owner. A clip that fails is regenerated with the next seed (`20260929`, then `20260930`); after three failures, rewrite only the TTS spelling (never the display text) — add a diacritic, respell a homograph — and record it; a sentence that still fails is an open item and the clip with the lowest error is used.
- **Homographs the transcription cannot judge** — کُرد/کرد ("Kurd"/"did"), کَسری (the hospital / "deficit"), سَقِّز, ژِن — are listed with their timestamps in `owner_listening_sheet.md` for the owner's ear.
- **Fallback.** If the voice service is unavailable, the film is delivered with the voice-free picture timed to the estimate of 121 words per minute, the score and ambience only, and burned-in subtitles carrying the narration; `open-items.md` records that the narration must be generated later and `owner_listening_sheet.md` explains how to mux it without re-rendering the picture (the cue sheet is the contract).

### 9.3 Music and ambience (designed, within §9.1)

The panel's sound designer proposed — as a spark, not a rule — *air and one instrument*: designed ambience as the spine (a city at a distance, wind in plane trees, a corridor's hum, wind over open ground at Aichi cemetery, the paper of a card, breath), and a single plucked string instrument built in code (a setar-like long-necked lute: a plucked string model with a fretted pitch table, a thin bridge buzz and a sympathetic course) playing short phrases in free metre at four to six moments only, in a mode of the Shur family (for example its sub-mode Bayat-e Kurd, a Kurdish name inside the Persian classical system), its intervals tuned as the tradition tunes them (the second degree of Shur sits roughly 130–160 cents above the tonic), never snapped to equal temperament; a breathy end-blown flute (ney-like) heard once, at the grave; the last phrase of the film stopping one step above its home note, unresolved. Avoid modes and gestures that read as triumph or as exotic cliché (augmented-second scales, generic pads, frame-drum grooves, wordless vocalise). Other directions are welcome if they keep §9.1. Never a chiptune or "8-bit" idiom.

Sound and picture share a clock: where the picture cycles a palette (water, smoke, light), the ambience may breathe on the same period; where a line is drawn, its stroke may have a faint sound of its own (marker on card, a thread).

### 9.4 Mix, placement and stems

- The narration is placed by the cue sheet (§10.3); the music is written into the voice's rests. Where music and voice overlap, the music is at least 10 dB below the voice (short-term loudness of the stems) with 8–10 dB of ducking (attack about 120 ms, release about 600 ms); ambience ducks only 4–6 dB so the world never vanishes.
- Room tone is never digital zero: every voice-free span has its place's own air (noise floor above −65 dBFS).
- Write the stems beside every final mix: `audio/<F>_stem_voice.wav`, `audio/<F>_stem_music.wav`, `audio/<F>_stem_ambience.wav`, so a take can be swapped and the mix rebuilt without touching the picture (`owner_listening_sheet.md`).
- The L and P mixes are separate (P has its own narration subset and its own timeline). The `_fa` and `_en` versions carry the same audio as their clean master.

---

## 10. How this studio works (method)

The method serves one goal: the best film this studio can make within a fixed amount of time. Ideas are judged while they are cheap — as a written treatment, as still frames, as short clips — and the full films are rendered once, at the end. Generation and critique are separate steps; reviewers see the evidence, never your summary.

### 10.1 Time: the budget and the living plan

- **Budget.** The whole production, from §5 to §14.7, has 4 to 8 hours of wall-clock time on this machine. Aim to finish in about 6 hours. **Eight hours after `started_utc` is a hard limit.**
- **The plan.** In Stage 0, write `plan.md`: one row per stage of this section with its planned minutes, the planned UTC time at which it ends, and the projected finish. Start from §15 and adjust to this film.
- **Adapt it at every stage.** At the end of every stage, append the actual UTC time (`date -u`), the elapsed time and a re-projected finish, and re-plan what remains. When the projection passes 7 hours, cut scope by the ladder of §10.13, one rung at a time; record every cut and its reason. Time saved goes to whatever improves the film most — usually the hero frames.
- **Deadlines.** The final render (Stage 7) starts no later than 5 h 45 min after `started_utc` with whatever look is locked then. At 8 hours, stop improving: let a running render finish, complete the mux, the checks and the records with what exists, and list everything unfinished in `open-items.md`.
- **Never idle, never unattended.** Long jobs may run as separate processes; check them regularly and use the time for work that does not compete for the GPU (sound, subtitles, records, review evidence). Never end a stage, or the production, while a job you started is still running.

### 10.2 Stage 0 — Pre-flight, reading and the plan (gate: `run.json` and `plan.md` exist)
Do §5. Read this brief fully once before writing code. Read `reference/woman-life-freedom/INDEX.md`, open every reference photograph of §7.3 once, and skim the dossiers' sections on the facts the narration uses. Write `plan.md` and start `decisions.md` with the interpretations you already anticipate.

### 10.3 Stage 1 — Narration lock and timing lock (gate: §7.5 items 1, 2 and 4 pass; `build/timeline.json` written)
1. Write `build/script_fa.json` from §7.2 (verify its sha256) and `build/strings.json` from §6.4.
2. Choose the voice (§9.2): calibration paragraph in at least three eligible voices, measured, recorded.
3. Generate every sentence of the L and P scripts as its own clip; verify each by transcription; regenerate failures (§9.2).
4. **The cue sheet.** Measure every clip's duration and write `build/cue_sheet.json`: `{sentence_id, beat, format, duration_s, wav, sha256, wer, seed, voice_id, model}`.
5. **The timing lock.** For each format, compute every beat's length = image pre-roll (≥ 1.5 s before the first sentence, more if a work appears first) + Σ sentence durations + the gaps of §6.5 + the beat's voice-free minimum + designed holds, within the beat's range of §8. If the picture would exceed its maximum, drop the optional lines in the order §7.2 gives (never a sentence of beat 3); if it falls short, lengthen holds. Write `build/timeline.json` (§8) with frame-exact times (`f = round(t × 60)`), `N_L` and `N_P`. From here on the timeline never changes; a later change requires re-running this step and recording why.
6. Write the subtitle cues from the timeline (§6.4) and the sidecar files of §3 row 6.

### 10.4 Stage 2 — The treatment and review 1 (gate: `reviews/review_1_notes.md` written)
1. **The moments.** Write in `decisions.md` one line beginning `The moment:` for each image of §7.4 that must land — what the viewer sees, and at which timeline second.
2. **The treatment.** Write `lookdev/treatment.md` (two pages at most): two or three genuinely different directions for the whole film (§7.4's sparks or your own) in a paragraph each; then, for the favoured one: the drawing style, the light clock and palettes, the reserved accent, how each work is entered and left, the transitions and the two (or fewer) hard cuts, the shot list per beat for L and how P differs, how beat 3's equal treatment is staged, how the count and the red water are staged, the sound idea, and which entries of `reference/craft/` informed it.
3. **Reading sheets.** Write `lookdev/reading_sheets/<work>.md` for each work you will draw (§6.1).
4. **Review 1 — the plan** (§13): the panel reviews the treatment and the timeline. Choose the direction, fold the accepted changes in before anything is built.

### 10.5 Stage 3 — The engine (gate: the grid, palette and provenance checks pass on test frames)
Build the page and tools: the indexed frame buffer and palette resolve; the layer/parallax system snapped to the grid; your rasterizer with coverage-to-palette anti-aliasing; string-map pixel sprites; the text rasterizer for the verified strings (dot check); the render driver with identity (Appendix A.3); the upscale and encode tool (Appendix A.4); and gates B01–B05 and F01–F02 runnable on any frame. Render ten test frames and pass them through the gates.

### 10.6 Stage 4 — Look development and review 2 (gate: the look is locked)
1. **Hero scenes.** Build and render, in L at full specification (native, then enlarged), the hero frames of four hero scenes and one hero place: W1 (two frames: the epitaph being written in beat 1, the last word in beat 9); the grave portrait behind glass (beat 4); Keshavarz Boulevard (beat 5); the hair becoming «ژینا» (beat 7); and the place of beats 2–3 in its first state — a street, door or window that must hold 30 s of attention through light alone, a generic Tehran place never identifiable as a specific street the facts do not name. Save to `lookdev/iter_N/`.
2. **Iterate.** Critique each frame against §6.11 in `lookdev/iter_N/critique.md` — what is default, muddy, pixelated-looking, flat, dead or overdone; what is beautiful — make the three changes that raise the lowest scores most, and render again. Run the still-frame checks on every iteration (grid, palette, text, contrast, safety: B03, B04, D01–D05, C02). Iterate at most four times or 100 minutes in total, whichever comes first, aiming at 8.5 on every line; then lock what you have and record the scores.
3. **The other scenes.** Every remaining scene is at least a lit hold with up to three layers and one living element, at 7.5 or above on every line, sharing the engine, palettes and light of the heroes; render one frame of each. More where time allows.
4. **P.** Recompose the hero frames for the portrait grid and bring them to the same look.
5. **Review 2 — the look** (§13). Make the accepted changes; render the affected frames once more.
6. **Lock the look.** Write `lookdev/selected.md` (the look in words, final scores, what the iterations taught) and `build/look.json` (every designed value the renderer reads: palettes, shots, transitions, cuts, the accent, the poster frames).

### 10.7 Stage 5 — Motion: animatic, key clips and review 3 (gate: `reviews/review_3_notes.md` written and its accepted changes made)
1. **Animatic.** Both formats at native resolution, full length, 30 fps is acceptable, with the voice placed and a draft mix (`build/animatic_<F>.mp4`), and contact sheets. Confirm every beat against `timeline.json`, every voice-free span, every transition, the two images of §7.4.
2. **Key clips** at full specification, in L: the opening (0–8 s), beat 3 whole (the three accounts, checked for equal treatment), the turn at Saqqez (the slogan's assembly), the hair becoming the name (6 s either side), the last word and the entry into the gallery; in P, the hair becoming the name. Run the motion checks on the clips (C01, C03, B05).
3. **Review 3 — the motion** (§13). Make the accepted changes; re-render only the clips they touch.

### 10.8 Stage 6 — Score and ambience (gate: stems written for both formats)
Compose and synthesise the music and the ambience against `timeline.json` (§9.3); render the stems; build a draft mix for review 3 if not already done.

### 10.9 Stage 7 — The final render (gate: exact frame counts, every identity verified, every grid check clean)
Render L and P once at the native grid, losslessly, with at most two pages at a time (§11.4); verify identities; write the native archives (§3 row 8); enlarge and encode the clean masters; enlarge the clean native frames × 4, overlay the cue images drawn at that size (§6.4), and encode the `_fa` and `_en` versions. While it renders, finish the sound and the evidence for the final look.

### 10.10 Stage 8 — Mix and mux (gate: loudness in spec)
Final mixes for L and P; two-pass loudnorm; mux into every video of the format (Appendix A.6).

### 10.11 Stage 9 — Automated checks (gate: `qa/qa_report.md` with no unexplained failure)
Run §12. One fix pass at most: fix the cause, re-render only the segments a defect touches, re-run the affected checks. Whatever remains goes to `open-items.md` with its measured value.

### 10.12 Stage 10 — Final look and finalization (gate: §14 complete)
The panel's final look (§13.4); fix only the defects it names, by segment, if the plan allows; then credits, licence, listening sheet, manifest, README, postmortem, open items and the final directory check (§14).

### 10.13 The scope ladder
When `plan.md` projects a finish beyond 7 hours, cut in this order, one rung at a time, and record each cut: (1) look iterations beyond the current one; (1b) non-hero scenes reduced to one lit hold each; (2) W6 (Amir Kabir) and other optional elements; (3) the second and third alternative directions' sketches; (4) the depth of the non-hero scenes (simpler staging, still ≥ 7.5); (5) score alternatives (keep one design); (6) the P key clip; (7) the depth of the P restaging (the same look with simpler compositions); (8) the fix pass of Stage 9 (failures become open items). Never cut: the narration and its verification, the fixed layer (facts, strings, depiction rules, fairness, credits), the six videos, the subtitles, legibility and flash safety, the three reviews (shorter, never skipped) and the records.

### 10.14 Separation of duties
One studio plays every role, so separation is enforced by sequence and evidence: the builder never grades their own work from memory. Run every review of §13 as a separate step: open only that review's evidence and the reviewer's brief, write the review in one sitting, and do not open `decisions.md` or earlier reviews until it is saved.

---

## 11. Engineering notes (traps already found on this machine)

### 11.1 Interfaces
- The page exposes `window.renderFrame(i, {draw})` (advances to `i`, updates every simulated history — hair, cloth, smoke, water, drawn strokes — in order, draws unless `draw === false`), `window.probe()` (§12.0), `window.__renderer`, `window.__ready`; it honours `?format=L|P` and `?notext=1` (hides every non-diegetic text: the optional title and date card, the credits). `renderFrame(i)` with `i` below the current frame rebuilds from frame 0.
- The page renders into a canvas of exactly the native size (480×270 or 270×480) at device scale 1, with CSS `image-rendering: pixelated` irrelevant because nothing is scaled in the page: the capture is native.
- Every render process logs its full encoder command line, every console message, every page error, every request URL (gate F01 reads this log), the renderer string, the identity check and one timing line per frame.

### 11.2 Determinism
Simulations (hair strands, cloth, smoke, water) step at a fixed `dt` from frame 0 with seeded randomness; their state is a function of the frame index. Rendering-side transcendental functions are harmless; a simulation that must agree between Node and the browser is baked once and read back (or written with IEEE-exact operations only).

### 11.3 Capture and identity
- Capture each frame at native size with the DevTools `Page.captureScreenshot` (PNG, `clip.scale: 1`) and pipe it to ffmpeg writing FFV1 rgb24. At native size a frame costs a few milliseconds to read back; the render is dominated by your drawing.
- Under load the fast capture has returned **stale frames**. Every captured frame carries an identity: the page draws the frame index into a strip of 16 cells below the picture (viewport `W × (H + 2)`; cells of `W/16` pixels, 2 pixels tall, most significant bit first) in the same task that renders the frame; the encoder crops the strip off and writes it to a side file; the driver decodes every frame's index after the segment and re-renders any segment with a mismatch (Appendix A.3).
- A segment that starts at frame `s > 0` first runs `renderFrame(k, {draw: false})` for every `k < s` so histories match the sequential render.

### 11.4 GPU and machine discipline
- Never run more than two rendering pages at once, never run heavy QA renders in parallel with a master render, and never start a render while another production renders on this machine.
- Detect context loss (`CONTEXT_LOST`, `DEVICE_LOST`, a `webglcontextlost` event) and stop with a non-zero exit; re-render that segment (up to three attempts, each recorded).
- Check `free -g` before each render group; if less than 8 GB is available, wait.

### 11.5 Enlargement and encoding of pixel art
- Enlarge with `scale=<W>:<H>:flags=neighbor:out_color_matrix=bt709:out_range=tv` from the lossless native file; never from a lossy file. Verified on this machine (2026-10-02, a worst-case test of random 6-pixel clusters from a 32-colour palette): after x264 at `-crf 12 -tune animation`, the largest variation inside any 8×8 block at 3840×2160 was 2.7/255 and inside any 4×4 block at 1920×1080 3.3/255; decoded block centres matched the native frame with a mean difference of 1.2/255; 600 frames at 3840×2160 encoded in 15 s.
- Subtitles are the declared exception (§6.4): enlarge the clean native frames to the version's size first, then overlay the cue images drawn at that size. Never enlarge a frame that already carries subtitles.

### 11.6 Persian and Kurdish text
- Shaping happens only when a whole string is drawn; a canvas `fillText` of single letters breaks joining. Set `direction = 'rtl'` (canvas) or `dir="rtl"` (DOM) for every Persian or Kurdish string.
- Thresholding a rasterized glyph to palette colours can delete the dots that distinguish letters (ب پ ت ث ی ن); check every drawn string with gate D03 and repair by hand in the pixel map.
- Erfan has no ZWNJ in its character map and no Sorani letters; verified here, it joins «نمی‌میری» into one word. Use it only for strings without ZWNJ; Vazirmatn shapes ZWNJ and Sorani correctly.

### 11.7 Records
Every heading in `decisions.md` carries the UTC time read from `date -u`. Every fallback, deviation and interpretation is recorded when it happens.

---

## 12. Automated checks (every check is mandatory)

These checks protect truth, fairness, safety, delivery and legibility; they never judge taste — taste is the panel's job (§13). Write one script, `tools/qa/gates.*`, that runs them all and writes `qa/qa_report.md` with one row per check: id, check, measured value, threshold, PASS/FAIL, evidence path. Never write or edit the report by hand and never relax a threshold. A FAIL that cannot be fixed within the time plan stays a FAIL, with its explanation in `decisions.md` and a row in `open-items.md`. The cheap checks (B03–B05, C01–C03, D01–D05) also run on stills and clips in Stages 4 and 5.

### 12.0 Inputs
1. **Probe.** The render driver calls `window.probe()` after each `renderFrame(i)` of the final render and appends its JSON line to `qa/probe_<F>.jsonl` (for stills and clips in Stages 4–5, the same for the frames rendered; no separate probe pass is run): `{frame, t, beatId, shotId, sentenceId, subtitleText, subtitleRect, drawnStrings: [{id, state, rect}], palettes: [ids], blend: {a, b, w} | null, transition: true|false, elements: [{id, rate, drawingIndex}], faceRects: [{kind, rect}], workIds, musicOn, stillness: true|false}`. `subtitleRect` is the bounding box of everything the cue image draws, outline and backing band included, padded by 4 delivered pixels; `kind` is one of `jina`, `jina_mark`, `private_featured`, `private_silhouette`.
2. **Native frames** (the lossless archives) for the grid checks; decoded deliverables at 2 fps and 10 fps for safety checks.
3. **Audio**: the stems, the mixes, loudnorm JSON for every deliverable, and the voice transcriptions.

### 12.1 A — Delivery
| id | check | method | threshold |
|---|---|---|---|
| A01 | Container | `ffprobe`; MP4 box order | `h264` High, `yuv420p`, dimensions of §3, `60/1` fps, bt709 primaries/matrix/transfer, tv range; `moov` before `mdat` |
| A02 | Frames | `-count_frames` | every L video `N_L` frames, every P video `N_P`; duration = frames / 60 ± 0.001 s |
| A03 | Audio stream | `ffprobe`; WAV samples | one AAC stream, 48 kHz, stereo, ≥ 224 kb/s; samples = frames × 800; audio and video durations within 1024 samples |
| A04 | Loudness | `loudnorm print_format=json` on each deliverable | −17.0 ≤ I ≤ −15.0 LUFS; true peak ≤ −1.0 dBTP |
| A05 | Versions agree | decoded `_fa`/`_en` vs clean master, outside subtitle rectangles, at 1 fps | mean abs diff ≤ 2/255 after scaling the master to the version's size by nearest neighbour |
| A06 | Sidecars | parse every `.srt`/`.vtt` | valid; cue times equal the cue sheet within 1 frame; texts equal §7.2's subtitle columns |

### 12.2 B — Integrity and the grid
| id | check | method | threshold |
|---|---|---|---|
| B01 | Frame identity | identity files of every segment | 0 mismatches |
| B02 | Determinism | native frames at 0, the middle and the last frame of each format rendered in two fresh sessions | 0 differing pixels |
| B03 | Integer grid | every 10th frame of each decoded master and version (subtitle rectangles excluded): per block of the format's scale, aligned to the frame origin | max in-block deviation ≤ 8/255; block centres vs the native frame: mean ≤ 2/255 |
| B04 | Palette | every native frame | every pixel colour ∈ `palette(i)` (or the declared union during a declared transition); `palette(i)` has ≤ 48 entries (≤ 96 in a declared transition); the gallery uses its single gallery palette |
| B05 | Drawing rate | probe `elements` | each element's `drawingIndex` changes only on its drawing frames (every `rate` frames from its phase); `rate` between 2 and 8, or a longer hold, for every element except a line's growing tip |

### 12.3 C — Picture safety and depiction
| id | check | method | threshold |
|---|---|---|---|
| C01 | Flash safety | 10 fps set at 270 px: mean luma per sample | at most 3 changes > 20/255 in any 1.0 s window; no single change > 40/255 except on a declared cut |
| C02 | Faces | probe `faceRects` | every figure sprite reports a face entry (a figure without one is a FAIL); `private_featured` ≤ 8 art pixels tall; `private_silhouette` any size, its face rectangle using at most 2 palette entries and no feature pixels; `jina` only on frames whose `workIds` include W2, W11 or W12, never taller than 50 % of the frame; `jina_mark` only with W9 or W10, under 16 art pixels |
| C03 | Never dead | native frames: count of native pixels that differ from the frame 30 frames earlier | in every 2 s window at least one pair with ≥ 4 changed native pixels; exempt only the gallery's final held frame (≥ 2 s), declared hard-cut frames, and at most three declared stillnesses in `look.json` (each ≤ 4 s, each justified in `decisions.md`) |
| C04 | No red flood | native frames | no frame with more than 25 % of its pixels in the red hue band (OKLCH hue 0–40° or 340–360°, chroma > 0.12), except W8 frames, where the red is maroon (OKLCH L ≤ 0.45) |

### 12.4 D — Text
| id | check | method | threshold |
|---|---|---|---|
| D01 | Strings exact | probe `drawnStrings`, `subtitleText`; `strings.json` | every drawn string id is in §6.4's table or is a declared partial state of T1/T2; every subtitle text equals its cue in §7.2 byte for byte after NFC |
| D02 | Subtitle timing | probe vs cue sheet | each cue visible from its sentence start (± 2 frames) to 0.3 s after its end or the next cue; no cue in a voice-free span; never two cues at once |
| D03 | Dots and marks | each diegetic string's pixel map declares its dots and marks as named components (`dot`, `vmark`) | the declared count equals the count expected from the string's letters (fixed table: ب1 پ3 ت2 ث3 ج1 چ3 خ1 ز1 ژ3 ش3 ف1 ق2 ن1, initial/medial ی2, final ی0, ێ and ڕ one `vmark` each); each declared component is present in the rendered native frame and separated from every stroke by ≥ 1 art pixel of another colour; square Kufic may realise a dot as one grid cell; partial states are checked on the letters drawn so far |
| D04 | Contrast | subtitle rectangles on the `_fa`/`_en` native frames | contrast of glyph colour against the mean colour behind ≥ 4.5:1 |
| D05 | Safe areas and limits | probe `subtitleRect`, computed font sizes | inside §6.4's band; ≤ 2 lines; ≤ 90 % of the frame width; font sizes within ±8 % of §6.4 |
| D06 | Words | every on-screen string, every subtitle, `README.md`, `CREDITS.md` | no `!`; no imperative to the viewer; none of `share, follow, subscribe, comment, like, wait for it, you won't believe, shocking, insane, epic, ultimate, hero, villain, martyr, regime, riot` outside quoted attributions in the subtitles of §7.2 |

### 12.5 E — Structure and fairness
| id | check | method | threshold |
|---|---|---|---|
| E01 | Timeline | `timeline.json` vs §8 | beat order, every beat length within its range, picture total within §6.2 |
| E02 | Voice-free | stems: voice RMS per 50 ms; timeline | every beat's voice-free minimum is one unbroken span with voice below −50 dBFS; the picture's voice-free share ≥ 30 % |
| E03 | Voice rules | cue sheet | ≥ 1.5 s from a work's first appearance to the first sentence; ≥ 0.5 s after any cut; gaps within §6.5; no continuous voice > 20 s |
| E04 | Equal accounts | beat 3 in the timeline and the probe | each account's span (authorities B3.1; family B3.2; UN mission and Iran's rejection B3.3–B3.4; in P: P3, P4, P5) ≥ 70 % of the longest; `musicOn` false throughout; one `shotId` composition (or three declared equivalent shots) with no camera move |
| E05 | Cuts | probe `shotId` vs `look.json` | at most two hard cuts, each declared |
| E06 | Red fountains | probe `workIds`, timeline | no frame with W8 lies inside beat 6 or within 10 s of a `death: true` sentence; W8 frames carry no voice |

### 12.6 F — Provenance
| id | check | method | threshold |
|---|---|---|---|
| F01 | No reference enters the film | (a) the render and probe logs list every request; (b) `grep -rnE 'reference/\|woman-life-freedom\|studio-briefs-v3/reference' src/ tools/ audio/` excluding `tools/qa/gates.*` and `tools/qa/truth.*`; (c) in `src/`: `new Image`, `<img`, `fetch(` of an image type, `ImageBitmap` from a URL or Blob, CSS `url(` other than the fonts, and `drawImage(` / `texImage2D(` whose source is not a canvas, OffscreenCanvas or ImageData created in the page; (d) every path opened by Python and Node tools | (a) only the studio's own `src/` files and the three fonts; (b) 0 lines; (c) 0 occurrences; (d) every path resolves under `RUN` |
| F02 | Fonts | requests and `assets/fonts/` | only the three fonts of §5 item 5, with matching sha256 |

### 12.7 G — Sound and voice
| id | check | method | threshold |
|---|---|---|---|
| G01 | Narration verified | `audio/voice/stt/*.json` | character error rate ≤ 5 % per sentence after §9.2's normalization; every proper noun of each sentence present; language Persian |
| G02 | Narration exact | `audio/voice/manifest.json` | every clip's text equals its sentence's TTS text; one voice and one model for the whole film |
| G03 | Clean signal | normalized WAVs | largest jump between consecutive samples ≤ 0.25 full scale; abs(mean) < 0.001; no sample at ±32767 |
| G04 | Never digital silence | mix | every 0.5 s window above −65 dBFS except the final 1.5 s fade |
| G05 | Music silent under death and dispute | music stem RMS over every `death: true` sentence and over beat 3 | below −60 dBFS |
| G06 | Restraint | music stem; mix short-term loudness | music above −50 dBFS for ≤ 35 % of the running time; the loudest 20 s window of the mix does not lie in the last 20 s of the picture |
| G07 | Voice over music | stems, short-term loudness during every sentence | voice at least 10 dB above music |
| G08 | No key in the run | `grep` of `RUN` for the key's first 8 characters | 0 matches |

### 12.8 H — Truth
| id | check | method | threshold |
|---|---|---|---|
| H01 | Truth checks | §7.5 | exit 0 |
| H02 | Credits | `CREDITS.md` and the gallery's drawn strings vs §7.3 | every work shown is credited exactly as §7.3; no work shown that §7.3 does not list |
| H03 | Licence | `LICENSE.md` | names CC BY-SA 4.0 and the share-alike sources |

### 12.9 L — Records
| id | check | method | threshold |
|---|---|---|---|
| L01 | Deliverables | the rows of §3; `sha256sum deliverables/*` vs `manifest.json` | all present and matching |
| L02 | Time plan | `plan.md` | planned and actual times for every stage, re-projections and scope cuts; elapsed ≤ 8 h or the overrun explained |
| L03 | Reviews | `reviews/` | reviews 1–3 with all five reviewers and the final look; every change has a disposition |
| L04 | Records | `decisions.md`, `README.md`, `postmortem.md`, `open-items.md`, `owner_listening_sheet.md` | headings carry `date -u` times; README and postmortem as §14; every failed check in `open-items.md` |

---

## 13. The panel (three reviews and a final look)

Reviews happen where changes are cheap: on the treatment, on still frames and on short clips — never on a finished film that would have to be rendered again. Each reviewer writes from the stated perspective, as a separate step that sees only that review's evidence (§10.14). Technical correctness is not the panel's job: the checks cover it.

### 13.1 The panel
- **The art producer** — the creative lead of a studio that makes animated documentaries and title sequences, deciding whether this film goes on the studio's reel. Judges the images that must land, wonder, the arc as a first-time viewer feels it, coherence, ambition; scores rubric lines 1, 8, 9 and 10; names the single biggest problem and one bold idea.
- **The pixel-art director and cinematographer** — a master of modern pixel art and of light. Judges pixel craft, light, depth, composition, palette, the likeness of Jina's portrait where it is drawn, and whether anything looks degraded from a photograph; scores lines 2–5.
- **The editor and motion designer** — a documentary editor who also designs titles. Judges pacing, holds, transitions, the two cuts, the voice-free spans, the subtitles' placement and legibility; scores lines 6 and 7.
- **The sound designer** — a film sound designer and composer at home in Persian classical music. Judges the voice choice, the score's restraint and tuning, the ambience, silence and the mix.
- **The standards editor** — an editor of an international news organisation's documentary unit. Judges fairness and dignity: does any image, transition, light, sound or juxtaposition suggest a version of a disputed event, make anyone a hero, villain or spectacle, or endanger anyone; are the accounts treated equally; is anything said or drawn that §7 does not support. Scores line 10 jointly with the art producer; any "no" from the standards editor is a change that must be made.

Each review is at most one page: **Scores** (the reviewer's lines, a sentence each; in review 1 the score is for what the plan promises), **What works** (one or two sentences), **Changes** (exactly three, ranked by impact: what, where, which rubric line or rule it serves, concrete enough to implement without a conversation, never touching the fixed layer) and **Verdict** (yes or no, one sentence). The art producer adds **The biggest problem** and **The bold idea**.

### 13.2 Evidence per review (in `reviews/review_N/evidence/`, built fresh for each review)
- **Review 1 — the plan:** `lookdev/treatment.md`, §7 of this brief, `timeline.json` as a readable table, the voice candidates' measurements, any sketch frames.
- **Review 2 — the look:** the latest hero frames at full size and at 270 px wide, one frame of every other scene, the P hero frames, the self-critique scores, the palettes as swatches.
- **Review 3 — the motion:** the animatic and its contact sheets, the key clips as files and as frame strips (every 6th frame), the draft mix's waveform and spectrogram, the voice-free spans marked.
- **The final look:** the posters, contact sheets of the finished films, frames of L at the start of every beat and at both images of §7.4, a subtitle frame of each version, the check summary.

### 13.3 Notes and changes
After each review, write `reviews/review_N_notes.md`: the five reviews' changes merged, conflicts resolved with a reason, each change with a disposition — **done**, **partly** (what and why) or **not done** (only when the fixed layer forbids it or the time plan has no room, said plainly). The art producer's first change, the pixel-art director's first change and every standards-editor change are always done unless the fixed layer forbids them. Add the panel's scores to the stage's row in `plan.md`.

### 13.4 The final look
After the checks, the art producer and the standards editor look at the finished film's evidence (§13.2) and write `reviews/final_look.md`: scores on all ten rubric lines, the defects that must be fixed now — a broken frame, unreadable text, a sound fault, a depiction or fairness fault; never a redesign — and a one-sentence verdict each. A defect is fixed by re-rendering only the segment it touches, once, if the time plan allows; otherwise it becomes an open item.

---

## 14. Finalization

### 14.1 `deliverables/manifest.json` schema

```json
{
  "brief": "jina", "brief_version": "1.0", "title": "ژینا — Jina",
  "run_dir": "<RUN>", "started_utc": "<ISO>", "finished_utc": "<ISO>", "elapsed_h": 0.0,
  "seed": 20260928,
  "tools": {"node": "", "python": "", "browser": "", "ffmpeg": "", "gpu_renderer": "", "fonts": []},
  "timeline": {"N_L": 0, "N_P": 0, "picture_L_s": 0.0, "picture_P_s": 0.0, "voice_free_share_L": 0.0, "voice_free_share_P": 0.0},
  "deliverables": [{"file": "", "sha256": "", "bytes": 0, "width": 0, "height": 0, "frames": 0, "duration_s": 0.0,
                    "loudness_out": {"I": 0, "TP": 0, "LRA": 0}}],
  "voice": {"model": "", "voice_id": "", "voice_name": "", "clips": 0, "max_sentence_cer": 0.0, "regenerated": 0},
  "look": {"look_sha256": "", "iterations": 0, "hero_scores": {}, "accent": "", "cuts": [], "poster_frames": {}},
  "works_shown": [],
  "checks": {"passed": 0, "failed_with_explanation": 0},
  "reviews": [{"review": "plan|look|motion|final", "verdicts": {"art_producer": "", "pixel_art_director": "", "editor": "", "sound_designer": "", "standards_editor": ""}, "changes_done": 0, "changes_total": 0}],
  "time": {"stages": [{"stage": "", "planned_min": 0, "actual_min": 0}], "scope_cuts": []},
  "open_items": 0
}
```

### 14.2 `deliverables/README.md`
Sections, in order: what the film shows (three sentences, no adjectives of praise); the narration in Persian with its English translation; the works shown, with credits; the look in one paragraph (from `lookdev/selected.md`); the deliverable table with durations and checksums; how fairness was kept (the equal accounts, the silences, what is not shown); how to reproduce; the check summary; the panel's verdicts per review and the final scores; the time (planned and actual per stage, the scope cuts); the open items.

### 14.3 `CREDITS.md` and `LICENSE.md`
As §6.9. `CREDITS.md` also lists the fonts (Erfan, Vazirmatn, Noto Nastaliq Urdu; SIL OFL 1.1) and the voice model and voice name used for the narration.

### 14.4 `owner_listening_sheet.md`
For the project owner, a Persian speaker, to check by ear after the run: every sentence with its timeline second in L and P, its transcription and character error rate; the homographs and Kurdish words with their exact timestamps (§9.2); the runner-up takes kept in `audio/voice/alt/`; and the exact commands to replace one sentence's clip, rebuild the mix from the stems, and re-mux every video of the format without re-rendering the picture. Where any open item needs the owner's decision — rights clearances (the unknown mural painters; the Frankfurt wall's status), a human-verified Sorani or English subtitle — it is listed here too.

### 14.5 `postmortem.md` and the final directory check
Five things that went right and five that went wrong, each about the process, each one sentence with the stage number of §10; the timing table from `plan.md`; one paragraph on the single root cause behind most of the wrongs, if there is one. Then `find RUN -type f | sort`: every row of §3 exists; delete nothing; `sha256sum deliverables/*` matches `manifest.json`.

### 14.6 Escalation and BLOCKED protocol
Stop the run only when a prerequisite of §5 cannot be met after its fallback, or the base directory is not writable. Then write `RUN/BLOCKED.md` (or `<OUTPUT>/jina/BLOCKED-<timestamp>.md` if `RUN` could not be created) with what was attempted, the exact error text, what would be needed, and everything completed. An unavailable voice service is not a block (§9.2 fallback).

### 14.7 Done
The run is done when §3 is complete, `qa/qa_report.md` shows every check PASS or failed-with-explanation, the final look is written, `manifest.json` validates and `postmortem.md` exists — or when the 8-hour limit was reached and the delivery was completed with what existed. Write the deliverable table, the elapsed time, the panel's final verdicts and the open-items count as the last section of `deliverables/README.md`, and print the same lines as the last output of the run.

---

## 15. What to expect

Reference durations on this machine (a laptop with an integrated GPU); use them for the first `plan.md` and record your actual times:

| stage | reference |
|---|---|
| 0 Pre-flight, reading, the plan | 15–20 min |
| 1 Narration and timing lock (about 35 clips, transcriptions, cue sheet) | 30–45 min |
| 2 Treatment, reading sheets, review 1 | 20–30 min |
| 3 The engine and its gates | 45–60 min |
| 4 Look development (four hero scenes and the beats 2–3 place, other scenes, P) and review 2 | 150–180 min |
| 5 Animatic, key clips and review 3 | 40–60 min |
| 6 Score and ambience (mostly in parallel with 4–5 and 7) | 30–45 min |
| 7 Final render, enlargement, subtitles, encode | 30–50 min |
| 8 Mix and mux | 10–15 min |
| 9 Checks and one fix pass | 15–25 min |
| 10 Final look and finalization | 15–25 min |
| total | about 6.5 to 7.5 hours; 8 hours is the hard limit — watch the plan |

Measured costs: a native frame captures in a few milliseconds, so the render time is the time your page takes to draw; at 3840×2160, 600 frames encode in about 15 s, so all six videos encode in about 20 minutes; one Persian sentence takes a few seconds to generate and to transcribe.

What good looks like: every clip passes its transcription on the first or second seed; the timing lock lands in range without dropping a line; the panel's verdict on the plan is yes, or yes with changes; the hero frames reach 8.5 within four or five iterations; the final render starts on time; the checks pass on their first run except one or two defects fixed in the single pass.

Known pitfalls (check each): converting a reference photograph by program instead of redrawing it (gate F01, and the panel will see averaged mud); a crowd of tiny bouncing sprites that reads as a game; a face that is almost her and therefore not her (define the likeness once, draw it per work in that work's pose, check that all three agree); thresholded Persian glyphs that lose their dots; Persian strings drawn letter by letter; mixed pixel sizes from a stray scaled layer; alpha crossfades between works; bloom or blur applied as a filter; dithering that swims as a layer moves (anchor it to the layer); subtitles drawn at output size; the death statement scored with music; the three accounts given unequal pictures or durations; the red fountains placed near the count or a death sentence; tear gas drawn into the boulevard; an invented gesture or a figure staged to illustrate a sentence; a legible placard or flag left in a crowd; red that reads as blood; the epitaph drawn with the Ontario sign's variant spelling; the verse on the headstone mistaken for the epitaph; music that swells at the end; clips placed by hand instead of from the cue sheet; starting the final render late; reviewing a finished film instead of stills and clips; waiting idle on a render; GPU device loss under parallel load; stale captured frames; loudnorm in one pass; audio a few milliseconds longer than the video.

---

## Appendix A — Reference implementations (verified on this machine on 2026-10-02; use, extend or replace, and record)

### A.1 Seeded random numbers

```js
// mulberry32; one instance per purpose; draws in a fixed, documented order
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
```

### A.2 Easing (for camera and light; never for drawn pixels, §6.3)

```js
export const easeInOutCubic = x => { const y = -2 * x + 2; return x < 0.5 ? 4 * x * x * x : 1 - (y * y * y) / 2; };
export const clamp01 = x => Math.min(1, Math.max(0, x));
export const prog = (t, t0, d) => clamp01((t - t0) / d);
```

### A.3 Render driver (loopback server → headless Chromium → native capture with identity → lossless FFV1)

The page draws at the native size (480×270 or 270×480) at device scale 1 and reserves a 2-pixel identity strip below the picture (viewport `W × (H + 2)`); at the end of `renderFrame(i)` it writes the frame index into 16 cells, most significant bit first:

```js
const strip = document.createElement('div'); strip.style.cssText = `position:absolute;left:0;top:${H}px;width:${W}px;height:2px;display:flex;`;
const cells = []; for (let k = 0; k < 16; k++) { const c = document.createElement('div'); c.style.cssText = 'flex:1;height:2px;background:#000'; strip.appendChild(c); cells.push(c); }
document.body.appendChild(strip);
const stamp = i => { for (let k = 0; k < 16; k++) cells[k].style.background = ((i >> (15 - k)) & 1) ? '#fff' : '#000'; };
// inside window.renderFrame(i): ... draw the frame ...; stamp(i);
```

```js
// tools/render.mjs  usage: node render.mjs --format L --start 0 --end 600 --out renders/L_seg0.mkv
import { chromium } from 'playwright';
import { spawn } from 'node:child_process';
import http from 'node:http'; import fs from 'node:fs'; import path from 'node:path';
import { mkdir, appendFile, readFile } from 'node:fs/promises';
const arg = (k, d) => { const i = process.argv.indexOf('--' + k); return i > 0 ? process.argv[i + 1] : d; };
const has = k => process.argv.includes('--' + k);
const SIZES = { L: [480, 270], P: [270, 480] };
const format = arg('format', 'L'); const [W, H] = SIZES[format]; const STRIP = 2;
const start = +arg('start', 0), end = +arg('end', 0); const subs = arg('subs', 'none');
const out = arg('out', `renders/${format}.mkv`); const identFile = out.replace(/\.mkv$/, '.ident');
const log = arg('log', out.replace(/\.mkv$/, '.log')); await mkdir(path.dirname(log), { recursive: true });
const L = s => appendFile(log, s + '\n');
const root = process.cwd(); const mime = { '.html': 'text/html', '.js': 'text/javascript', '.mjs': 'text/javascript', '.json': 'application/json', '.ttf': 'font/ttf', '.bin': 'application/octet-stream' };
const srv = http.createServer((req, res) => { const p = path.normalize(path.join(root, decodeURIComponent(req.url.split('?')[0]))); if (!p.startsWith(root)) { res.writeHead(403); return res.end(); } fs.readFile(p, (e, d) => { if (e) { res.writeHead(404); return res.end(); } res.writeHead(200, { 'Content-Type': mime[path.extname(p)] || 'application/octet-stream' }); res.end(d); }); });
await new Promise(r => srv.listen(0, '127.0.0.1', r)); const port = srv.address().port;
const gpuArgs = ['--use-gl=angle', '--use-angle=vulkan', '--enable-features=Vulkan', '--ignore-gpu-blocklist'];
const browser = await chromium.launch({ headless: true, args: ['--force-color-profile=srgb', '--font-render-hinting=none', '--disable-lcd-text', ...(has('sw') ? [] : gpuArgs)] });
const page = await browser.newPage({ viewport: { width: W, height: H + STRIP }, deviceScaleFactor: 1, colorScheme: 'dark' });
let lost = false;
page.on('pageerror', e => { L('PAGE ERROR ' + e); process.exitCode = 2; });
page.on('console', m => { const t = m.text(); L('CONSOLE ' + m.type() + ' ' + t); if (/context lost|DEVICE_LOST|CONTEXT_LOST/i.test(t)) lost = true; });
page.on('request', r => L('REQUEST ' + r.url()));
await page.goto(`http://127.0.0.1:${port}/${arg('page', 'src/page.html')}?format=${format}&subs=${subs}`);
await page.waitForFunction(() => window.__ready === true, null, { timeout: 120000 });
await L('RENDERER ' + await page.evaluate(() => window.__renderer || 'unknown'));
const cdp = await page.context().newCDPSession(page);
// lossless native archive (FFV1 rgb24) + the identity strip as a 16×1 gray side file
const ffArgs = ['-y', '-f', 'image2pipe', '-framerate', '60', '-c:v', 'png', '-i', '-',
  '-filter_complex', `[0:v]split=2[a][b];[a]crop=${W}:${H}:0:0,format=bgr0[v];[b]crop=${W}:${STRIP}:0:${H},scale=16:1:flags=area,format=gray[id]`,
  '-map', '[v]', '-c:v', 'ffv1', '-level', '3', '-pix_fmt', 'bgr0', out,
  '-map', '[id]', '-f', 'rawvideo', identFile];
await L('FFMPEG ffmpeg ' + ffArgs.join(' '));
const ff = spawn('ffmpeg', ffArgs, { stdio: ['pipe', 'ignore', 'inherit'] });
const write = buf => new Promise((res, rej) => ff.stdin.write(buf, e => (e ? rej(e) : res())));
if (start > 0) await page.evaluate(s => { for (let k = 0; k < s; k++) window.renderFrame(k, { draw: false }); }, start);
for (let i = start; i < end; i++) {
  const t0 = Date.now();
  await page.evaluate(i => window.renderFrame(i), i);
  if (lost) { await L('CONTEXT LOST at frame ' + i); process.exit(3); }
  const { data } = await cdp.send('Page.captureScreenshot', { format: 'png', optimizeForSpeed: true, captureBeyondViewport: false, clip: { x: 0, y: 0, width: W, height: H + STRIP, scale: 1 } });
  await write(Buffer.from(data, 'base64'));
  await L(`frame ${i} ${Date.now() - t0}ms`);
}
ff.stdin.end(); await new Promise(r => ff.on('close', r));
await browser.close(); srv.close();
const id = await readFile(identFile); const n = id.length / 16; const bad = [];
for (let k = 0; k < n; k++) { let v = 0; for (let b = 0; b < 16; b++) v = (v << 1) | (id[k * 16 + b] > 127 ? 1 : 0); if (v !== start + k) bad.push([start + k, v]); }
await L(`IDENTITY frames ${n} expected ${end - start} mismatches ${bad.length}`);
process.exitCode = (n === end - start && bad.length === 0) ? (process.exitCode || 0) : 4;
```

Verified here: a test page drew 240 L frames and 120 P frames (the P segment starting mid-film at frame 100), every identity correct, the decoded FFV1 frame bit-exact against the drawn palette (0 differing pixels, exactly the palette's colours), at about 6× real time for a trivial page. Segments of about 3,000 frames; at most two render processes at once (§11.4). Concatenate the FFV1 segments with the concat demuxer and `-c copy`.

### A.4 Enlargement, subtitles and encode

```bash
# the clean master: native lossless → × 8, BT.709 limited range, 4:2:0
ffmpeg -hide_banner -y -i build/native_L.mkv \
  -vf "scale=3840:2160:flags=neighbor:out_color_matrix=bt709:out_range=tv,format=yuv420p" \
  -c:v libx264 -preset slow -crf 12 -tune animation -profile:v high -g 120 -keyint_min 60 \
  -colorspace bt709 -color_primaries bt709 -color_trc bt709 -color_range tv -an renders/L_video.mp4
# a subtitled version: the clean native frames × 4, then each cue image (RGBA PNG at 1920×1080) overlaid for its frames
ffmpeg -hide_banner -y -i build/native_L.mkv -i build/subs_fa/cue_001.png -i build/subs_fa/cue_002.png \
  -filter_complex "[0:v]scale=1920:1080:flags=neighbor[b];[b][1:v]overlay=enable='between(n,612,830)'[c1];[c1][2:v]overlay=enable='between(n,860,1101)',scale=out_color_matrix=bt709:out_range=tv,format=yuv420p" \
  -c:v libx264 -preset slow -crf 12 -tune animation -profile:v high -g 120 -keyint_min 60 \
  -colorspace bt709 -color_primaries bt709 -color_trc bt709 -color_range tv -an renders/L_fa_video.mp4
# P: scale=2160:3840 (× 8) for the clean master, 1080:1920 (× 4) for the versions
```

Measured here on a worst-case pattern (random 6-pixel clusters, 32 colours, moving): 600 frames at 3840×2160 encoded in 15 s (1.25 MB), at 1920×1080 in 4 s; largest in-block variation after decoding 2.7/255 (× 8) and 3.3/255 (× 4); decoded block centres vs native mean 1.2/255.

Grid check (B03) on a decoded frame:

```python
import numpy as np
def grid_check(frame_rgb, native_rgb, s):
    a = frame_rgb.astype(int); H, W = native_rgb.shape[:2]
    b = a[:H*s, :W*s].reshape(H, s, W, s, 3)
    dev = np.abs(b - b.mean(axis=(1, 3), keepdims=True)).max()
    centers = b[:, s//2, :, s//2, :]
    return dev, np.abs(centers - native_rgb.astype(int)).mean()
```

### A.5 Voice and transcription (the key is read at call time and never written anywhere)

```python
import json, urllib.request
KEY = [l.split('=', 1)[1].strip() for l in open('<CREDENTIALS_FILE>') if l.startswith('ELEVENLABS_API_KEY=')][0]
def tts(text, voice_id, out_mp3, prev='', nxt='', model='eleven_v4', seed=20260928):
    body = {"text": text, "model_id": model, "language_code": "fa", "seed": seed,
            "previous_text": prev, "next_text": nxt,
            "voice_settings": {"stability": 0.7, "similarity_boost": 0.75, "style": 0.0, "use_speaker_boost": True}}
    req = urllib.request.Request(f"https://api.elevenlabs.io/v1/text-to-speech/{voice_id}?output_format=mp3_44100_192",
                                 data=json.dumps(body).encode(), headers={"xi-api-key": KEY, "Content-Type": "application/json"})
    open(out_mp3, 'wb').write(urllib.request.urlopen(req, timeout=180).read())
# transcription (multipart): curl -s -H "xi-api-key: $KEY" -F model_id=scribe_v2 -F language_code=fa -F file=@clip.mp3 \
#   https://api.elevenlabs.io/v1/speech-to-text   → {"language_code": "fas", "language_probability": 1.0, "text": ..., "words": [{text, start, end, type}]}
```

Verified here: the seven-sentence calibration paragraph (B2.1–B3.4 of an earlier draft, 87 spoken words) with voice `ndcUYGFbbd96WXiZVVaQ` took 43.2 s on `eleven_v4` and 34.6 s on `eleven_v3`; both transcriptions matched the text word for word (the transcription writes numbers as digits and may drop a ZWNJ — normalize before comparing). `eleven_v4` ignored the `speed` setting. Shared voices can be used by `voice_id` directly.

### A.6 Loudness normalization (two-pass, −2.0 dBTP) and mux

```bash
ffmpeg -hide_banner -i audio/L_mix.wav -af loudnorm=I=-16:TP=-2:LRA=11:print_format=json -f null - 2> audio/L_measure.txt
# read input_i, input_tp, input_lra, input_thresh, target_offset from the JSON block, then:
ffmpeg -hide_banner -y -i audio/L_mix.wav -af "loudnorm=I=-16:TP=-2:LRA=11:measured_I=<input_i>:measured_TP=<input_tp>:measured_LRA=<input_lra>:measured_thresh=<input_thresh>:offset=<target_offset>:linear=true:print_format=json" -ar 48000 audio/L_norm.wav 2> audio/L_norm.txt
ffmpeg -hide_banner -y -i renders/L_video.mp4 -i audio/L_norm.wav -map_metadata -1 -c:v copy -c:a aac -b:a 256k -ar 48000 -ac 2 -shortest -movflags +faststart deliverables/jina_L.mp4
```

### A.7 WAV writer

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

Sample count: `frames / 60 × 48000` exactly (800 per frame).

### A.8 Contact sheets

```bash
ffmpeg -hide_banner -y -i deliverables/jina_L_fa.mp4 -vf "fps=0.25,scale=480:-1:flags=neighbor,tile=6x10:padding=4:margin=4" -frames:v 1 qa/contact_L.png
ffmpeg -hide_banner -y -i deliverables/jina_P_fa.mp4 -vf "fps=0.25,scale=270:-1:flags=neighbor,tile=8x3:padding=4:margin=4" -frames:v 1 qa/contact_P.png
```

---

End of brief. Begin with §5.

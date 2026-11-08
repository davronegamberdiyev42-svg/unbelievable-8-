# IELTS Boost — Stage 40 QA report

Build: 2026-11-08  
Release: `40.0.0`  
Target: GitHub Pages project path `/unbelievable-8-/`

## 1. Static and data validation

| Test | Result |
|---|---:|
| Embedded `appData` JSON parse | PASS |
| Searchable vocabulary records | 19,000 |
| First 4,000 entries contain US + UK IPA fields | 4,000 / 4,000 |
| Complete offline bilingual glosses (English definition + Uzbek meaning + example + POS) | 677 |
| Manifest JSON parse and exact `id`, `start_url`, `scope` | PASS |
| Manifest icons decoded at declared dimensions | 4 / 4 |
| Application inline JavaScript syntax (`node --check`) | PASS |
| Service worker JavaScript syntax (`node --check`) | PASS |
| MP3 assets parse with valid duration and bitrate | 84 / 84 |
| Total bundled synthetic listening audio duration | about 239.7 minutes |

Static QA script result: **32 / 32 PASS**.

## 2. Browser UI smoke tests

Chromium DOM smoke test used a local copy of the HTML with a simulated Web Speech Recognition event. **28 / 28 PASS**.

Validated:
- Stage 40 app boot and all 10 game modules render.
- Part 1, Part 2, Part 3 and daily challenge each have the correct transcript target.
- Simulated Part 2 speech is written to the Part 2 textarea and does not overwrite the daily challenge.
- Speaking analytics report and TXT export controls render.
- All ten modules show a mission, guide and submit control.
- Grammar answer selection and formative score submission work.
- Dedicated pronunciation mission is visible, with its own recorder, playback element and target phrase.
- Paraphrase has four semantic self-checks: claim, scope, certainty and time.
- Fluency has a distinct spoken-response transcript field and ASR control.
- Vocabulary search and resumable batch-lookup panel render.
- Settings exposes PWA readiness diagnostics.
- No uncaught page-level JavaScript errors in this smoke test.

Question-bank validation: **24 / 24 collocation items + 24 / 24 grammar items** have valid option indexes, focus notes and explanations. The 12 pronunciation practice prompts are present.

## 3. PWA / Android install validation

- Manifest `id`, `start_url` and `scope`: `/unbelievable-8-/`.
- Display mode: `standalone`; `prefer_related_applications` is `false`.
- Declared icons: 192×192 any, 512×512 any, 512×512 maskable, 96×96 maskable.
- Head links include manifest, PNG icons, SVG/ICO favicons and Apple touch icon.
- Service worker cache namespace is `ielts-boost-stage40`; core shell and app icons are precached atomically; optional favicon downloads do not block install.
- Audio assets use a separate cache and range-response handler.
- All PWA files and image dimensions pass static inspection.

A local HTTP server successfully served the HTML and manifest with HTTP 200. Chromium navigation to the local test server was blocked by the container administrator (`ERR_BLOCKED_BY_ADMINISTRATOR`), so service-worker control and native install were **not** claimed as browser-tested. Physical Samsung Galaxy A14 WebAPK/launcher-icon installation remains a device acceptance test.

Android note: Chrome may create a browser-badged shortcut rather than a WebAPK on devices without Google Mobile Services (GMS). A web app cannot force Chrome to create a native Android package. On Samsung devices, Samsung Internet is another supported PWA-to-WebAPK route. See the README/install guide for the user-side checks.

## 4. Vocabulary coverage — truthful counts

- 19,000 searchable records are bundled.
- First 4,000 have US/UK IPA fields.
- 677 entries are complete offline bilingual glosses, measured from actual bundled fields.
- First 4,000 are available to the on-demand Uzbek translation queue.
- First 9,000 are available to the on-demand English definition/phonetic lookup queue.
- Online results are cached locally on the learner's device. MyMemory translations are machine-generated and require sense verification. API rate limits, unsupported words and network failure can prevent full coverage.

Therefore, Stage 40 does **not** claim that 4,000 translations or 9,000 definitions are already fully bundled offline.

## 5. Acceptance tests still required on the real Samsung phone

1. Allow microphone permission for the HTTPS GitHub Pages origin; confirm live speech recognition on each Speaking segment.
2. Make a short Pronunciation Lab recording, stop it, replay it and reload the page to verify IndexedDB restore.
3. Open the published GitHub Pages URL, wait for service-worker activation, reload once, then check Settings → PWA readiness.
4. Remove the old home-screen shortcut and retry `Install app`. If Chrome offers only a browser shortcut, check that Google Play services is installed/enabled or use Samsung Internet's app-install flow.
5. Confirm offline reload after the first successful online visit; remote dictionary lookups still require internet.

## 6. Scoring and source boundaries

The mission score is an internal 0–10 learning metric, not an official IELTS band or a human examiner result. Transcript metrics are deterministic text signals. ASR confidence is recognition confidence, not pronunciation quality. Pronunciation must be reviewed from the stored audio; automated phoneme scoring is not claimed.

Bundled listening tracks are synthetic practice generated from original IELTS Boost scripts, not official IELTS/Cambridge/British Council recordings. Cambridge dictionary links and licensed publisher resources are opened externally rather than scraped and redistributed.

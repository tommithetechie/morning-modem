# The Morning Modem

**Signing on at 56k — yesterday's tech, reported like it's brand new.**

A weekly retro-tech radio show that reports yesterday's computers and gadgets as if they just hit the CES floor. English only; scheduled for **07:00 America/Chicago every week**. The schedule is station metadata, not an installed automation or a promise of an operating broadcast service.

- Intended preview: https://tommithetechie.github.io/morning-modem/
- Repository: https://github.com/tommithetechie/morning-modem
- Phase 1 only: **TEST PILOT — not for broadcast** (2026-11-05).
- Weather is off. Comments are not configured. No affiliate or payment links.

## Pilot

One opening, two source-backed retro news items, and a closing:

1. [IBM introduces the Personal Computer](https://www.ibm.com/history/personal-computer): August 12, 1981, at New York's Waldorf Hotel; USD 1,565, 16 KB RAM, and open design documentation.
2. [Commodore 64 debuts at Winter CES](https://spectrum.ieee.org/commodore-64): January 1982 in Las Vegas; USD 595, 64 KB memory, and in-house graphics and sound chips.

Each segment is a dramatized early-1980s news bulletin, not a claim that these products are new in 2026. The two reports move between their explicitly stated historical dates. No historical photographs or third-party article images are stored here.

The single-language episode uses `episodes/2026-11-05.json` and `audio/2026-11-05.mp3`. `episodes.json` lists its title and measured audio duration. Captions and segment boundaries are calculated from decoded per-line recordings with 0.25 seconds of silence between lines, not estimated from word counts. The final MP3 duration is measured with ffprobe.

## Voice and placeholder host

**Voice: Microsoft Edge TTS (en-US-AriaNeural)**

**Host: AI-generated character (placeholder).**

This is a stock synthetic neural voice, not a recording or custom clone of a real person. The template's sample character assets remain unchanged for the player test. They are a labeled placeholder, not a final host design and never historical evidence. The modem mark in `logo.svg` is an original drawn placeholder.

Speech is synthesized through the third-party `edge-tts` client using Microsoft Edge Read Aloud's online service. Review the applicable Microsoft Edge and [Microsoft Services Agreement / online-service terms](https://www.microsoft.com/en-us/servicesagreement). The client software's license is not a license to Microsoft's voice service or audio output. Public redistribution rights for Edge Read Aloud output have not been established by this project; the pilot is not cleared for broadcast or commercial reuse. Do not assume Azure Speech output-use rights apply to Edge Read Aloud.

## Files and local preview

```text
station.json              Station identity, schedule, credits, and audio retention
episodes.json             Single-language episode index
episodes/2026-11-05.json   Pilot script and measured caption/segment timing
audio/2026-11-05.mp3       Local recording, gitignored on the source branch
character/                Unchanged AI-generated placeholder character
logo.svg                  Original placeholder modem mark
index.html                Unmodified template player
AGENTS.md                 Template operating instructions
docs/formats.md           Station and episode format documentation
tools/publish.sh           Assemble committed HEAD plus recent local audio
tools/share.py             Generate local share-card assets during publication
```

For a local test, run `python3 -m http.server 8000` from this folder and open `http://localhost:8000/`. There is no application build or backend. A browser is required to verify actual playback, appearance, and caption sync.

## Publication and retention

All source changes belong on a new branch and a pull request for review. Do not merge as part of this phase. Never commit audio to the source branch or main; `audio/` is already gitignored.

After the station files are committed, `tools/publish.sh` archives the current **HEAD** (not necessarily main), copies local audio within `audio.keep_days` (30 days), generates share assets, and replaces the `gh-pages` branch. GitHub Pages must serve `gh-pages` at `/`. That replacement is an explicit publication action, not a local preview. Configure no recurring job in Phase 1. Retention is applied only when publication runs; it is not a timed deletion service.

## Attribution and licenses

The retained player and tools are MIT-licensed; preserve `LICENSE` and its upstream copyright notice. The original pilot script and episode index are CC0, consistent with the inherited script license. The sample character is reused under the template's express permission for non-offensive uses. The voice-service and generated-audio terms are separate from those source-code and script licenses.

# SoundHaus

**Play YouTube and record each track as it plays.**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

[**▶ Try it live**](https://samcheonghaus.github.io/SoundHaus/) · [한국어 README (Korean)](./README.ko.md)

SoundHaus is a recorder that runs from a **single HTML file**. Paste a YouTube link, the video plays inside SoundHaus, and each track is recorded from the exact moment it starts to the moment it ends — saved as **MP3, WAV or MP4**. No installation, no account, no server.

## How to use

1. Open [samcheonghaus.github.io/SoundHaus](https://samcheonghaus.github.io/SoundHaus/) in Chrome or Edge.
2. **Paste** a YouTube video or playlist link — it loads right away.
3. Press **[● Start recording]** → press **Share** once.
4. Recording stops when the track ends. **Save as MP3** from the list.

## Features

- **Track-accurate recording** — start and stop follow the player's own play / pause / ended signals, not silence guessing.
- **Whole playlists** — with "Whole playlist", every track becomes its own file **named after the video** (`01 Track title.mp3` …).
- **Player controls** — ⏮ ▶ ⏭ or the player itself. Pausing pauses the recording; skipping mid-track marks the earlier one as "partial".
- **Clean digital capture** — not through speakers or a microphone, so PC volume and room noise do not matter.
- **Formats** — MP3 (128–320 kbps), lossless WAV, and MP4 video cropped to the player.
- **Save all as MP3** — pick a folder once and save a whole playlist.
- **Trim silence**, **record your microphone too** (sing or play along).
- **Record another tab or app** — for sites other than YouTube or desktop apps; starts with the sound, stops after 2 s of silence.
- While recording, the tab title shows a **red ● and the time**, visible from any tab.
- Korean / English interface.

## Notes

- Works in **Chrome or Edge on a PC**.
- YouTube blocks playback inside pages opened directly from disk (`C:/…`). **Open the web address (GitHub Pages).** "Record another tab" works from a local file too.
- Videos whose owners disabled embedding will not play inside SoundHaus — use "Record another tab" on the YouTube tab instead.
- Ads that play before a video may be recorded too.

## Copyright

Use recordings for **personal listening only**. Re-uploading or distributing copyrighted music may infringe copyright; please also respect YouTube's Terms of Service. Recordings stay on your computer and are never uploaded.

## Tech

Single HTML file + vanilla JavaScript.

| Component | Used for |
|---|---|
| YouTube IFrame Player API | Playback and state events |
| Screen Capture API (`getDisplayMedia`) | Capturing the tab's audio (and video) digitally |
| Web Audio · AudioWorklet | Lossless PCM capture and level meters |
| MediaRecorder · Region Capture | MP4 video cropped to the player |
| [lamejs](https://github.com/zhuker/lamejs) (LGPL-3.0) | MP3 encoding — loaded from a CDN on first MP3 save |

## License

**GNU General Public License v3.0** ([LICENSE](./LICENSE)) · © 2026 Kim Jin Baek (samcheonghaus)

The single `index.html` file **is** the complete source code.

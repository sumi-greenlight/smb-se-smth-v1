# Yellow Pages Contact Profile – Voice Recorder Demo

This project contains a single, self-contained HTML page that demonstrates a simple CRM-style contact profile with a built‑in **voice recorder**, a **timer**, playback, and a **mock “Transcribe & Summarize”** action.

## Files

- `yellow-pages.html` – The full demo page (no build step required).

> If you don't have it yet, download the HTML from your chat message titled *Download the HTML*. Save it alongside this README.

## Features

- **Three‑panel layout** (left, center, right) with simple CRM styling.
- **Activity type chips** (Note, Email, Call, Meeting, Task).
- **Voice Recorder**
  - Start, pause/resume, and stop recording.
  - Live timer during recording.
  - Playback of the recorded clip.
  - Mock “Transcribe & Summarize” that reveals sample transcription and summary text.
- **Material Icons** via Google Fonts.

## Quick Start

1. Download `yellow-pages.html`.
2. Open the file directly in a modern desktop browser (Chrome, Edge, or Firefox recommended).
3. Click the **mic** button to start recording.

### Browser Permissions & Notes

- The page uses the **MediaRecorder API** and `navigator.mediaDevices.getUserMedia({ audio: true })`.
- On first use, your browser will prompt for **microphone access**. Click **Allow**.
- Most browsers require the page to be served from a secure context (**https://** or **localhost**) to access the microphone.
  - Opening the file directly (`file://`) may work in some browsers, but if not, serve it locally:
    ```bash
    # Python 3
    python -m http.server 8000
    # then open http://localhost:8000/yellow-pages.html
    ```

## How It Works (Overview)

- When you click **mic**:
  - We request an audio stream and start a `MediaRecorder`.
  - Data chunks are buffered and, on `stop`, converted into a Blob → Object URL for playback.
- **Pause/Resume** toggles the recorder and timer.
- **Transcribe & Summarize** is simulated with a timeout and displays static sample text (no external API calls).

## Customization

- **Branding & Colors:** Edit CSS variables in the `:root` section.
- **Initial Contact Info:** Update the name and left‑panel content in the HTML.
- **Real Transcription:** Replace the mock `transcribeAndSummarize()` with your own API call to a speech‑to‑text service.

## Known Limitations

- No persistence: recordings are kept in memory until you navigate away.
- Transcription is a mock; it does not process audio.
- Mobile browser behavior may vary (especially iOS).

## License

This sample is provided as‑is for demonstration purposes.

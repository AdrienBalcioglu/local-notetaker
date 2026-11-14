# Local Notetaker

Sticky notes that expire on their own, and voice notes transcribed on your computer. No API key, nothing uploaded.

**[Website](https://adrienbalcioglu.github.io/local-notetaker/about.html)** · **[Open the app](https://adrienbalcioglu.github.io/local-notetaker/)**

## Features

- Sticky notes that disappear after 1 hour, tonight, 24 hours or 7 days, unless you keep them
- Voice notes: record, and the text appears as a note
- Transcription runs on your device, in six languages or with automatic detection
- One click to copy a note

## Usage

Use the live demo, or serve the folder locally (the microphone needs `https` or `localhost`):

```bash
python3 -m http.server 8000
```

## How the local transcription works

- Speech is transcribed by [Whisper](https://github.com/openai/whisper), running in your browser through [Transformers.js](https://github.com/huggingface/transformers.js) and WebAssembly.
- **Your audio never leaves the computer.** There is no API key and no server.
- The speech model is downloaded once from Hugging Face, then kept in the browser cache: 41 MB (fast), 77 MB (balanced) or 249 MB (most accurate).
- The recording itself is not stored. Only the text is kept, in the browser's local storage.

The model makes mistakes, mostly on names and figures. Read the text before you rely on it.

## Stack

A single HTML file. Whisper through Transformers.js, loaded from a CDN at a pinned version.

## License

[MIT](LICENSE) © 2026 Adrien Balcioglu

# 🌐 Universal Downloader — Portable Windows x64

> **Portable Windows application for video/audio downloading, audio extraction, and stream capturing.**  
> **Created by Orion4D — 2026**

<img width="1348" height="1110" alt="image" src="https://github.com/user-attachments/assets/7669ce15-96e2-45ee-b6cf-4e595ffe52b8" />
<img width="1346" height="1034" alt="image" src="https://github.com/user-attachments/assets/949ad98b-b8ed-47d3-b798-8eaf5331f0c9" />

- **Latest release:** [Universal Downloader v3.0.0](https://github.com/orion4d/Universal_downloader_windows/releases/tag/V3.0.0)  
- **Direct download:** [UniversalDownloader-v3.0.0-Portable-win-x64.zip](https://github.com/orion4d/Universal_downloader_windows/releases/download/V3.0.0/UniversalDownloader-v3.0.0-alpha.1-Portable-win-x64.zip)

**Universal Downloader** is a portable Electron application powered by **yt-dlp**, **FFmpeg**, **FFprobe**, and **Deno**.

It allows you to parse, download, convert, and capture media from numerous platforms, featuring a clean GUI, download queue, presets, local history, and built-in diagnostic tools.

The interface is available in both **English** and **French**.

---

## 🤖 What's New in v3.1.0
Version 3.1 adds **native batch URL list management** without requiring Codex or Ollama.

Main additions:

- Import URL lists from `.txt`, `.md`, and `.csv`
- Automatic extraction of HTTP/HTTPS links
- Duplicate URL removal
- Native multi-selection interface
- Range selection, filtering, and batch queueing
- Multi-URL clipboard support
- Clear loaded playlist / URL list
- Full application Reset
- Faster first-run setup by skipping already installed tools

Each imported URL is analyzed automatically when it reaches the download queue.


## 🤖 What's New in v3.0.0
- Version 3 adds full **YouTube playlist support** to Universal Downloader while preserving all downloading, MCP and local Ollama features introduced in v2.


## 🤖 What's New in v2.0.0
Version 2 adds a local AI automation layer while keeping all the downloading, conversion, queue, history and stream-capture features from v1.

- **Local MCP integration** for Codex and compatible MCP clients
- **Local Ollama assistant** with tool calling
- **Real-time Ollama activity indicator** with current phase and elapsed time
- **Natural-language batch downloads**
- **Secure URL list import** from `.txt`, `.md` and `.csv` files
- **Paste button** next to the main URL field
- **Readable AI tool activity log**
- **Automatic completion summary** when the model executes tools without returning a text answer

Universal Downloader exposes only predefined actions to AI clients. It does **not** expose a generic shell or arbitrary command execution.

---

## ✨ Features

### 📥 Smart Downloading

- **Video + Audio**
- **Video only**
- **MP3 Audio**
- **Manual Video/Audio muxing**
- **Automatic formats or manual stream selection**
- **Automatic platform detection**
- **Pre-download media preview:**
  - Thumbnail
  - Title
  - Duration
  - Platform
  - Media ID
- **Download thumbnail as PNG**
- **Automatic URL sanitization**
- **Direct audio/video URL support**

Universal Downloader primarily relies on **yt-dlp** extractors.  
Actual platform compatibility therefore depends on the services supported by yt-dlp.

---

### 🎯 Download Profiles

Quick presets are available to avoid manually picking streams for each download:

- **Best Quality — Video + Audio**
- **MP4 — up to 1080p**
- **MP4 — up to 720p**
- **MP3 — 192 kbps**
- **MP3 — 320 kbps**

Dedicated tabs remain accessible to fine-tune and select specific audio or video streams.

---

### 🎵 Audio Extraction

Universal Downloader can extract and convert audio to MP3 format.

Available presets:

```text
MP3 192 kbps
MP3 320 kbps
```

Audio conversion is powered by **FFmpeg**.

Direct audio streams are also supported, such as:

```text
.mp3
.aac
.m4a
.ogg
.opus
.wav
.flac
```

---

### 🖼️ Thumbnail Download

After parsing a video URL, the button:

```text
Download PNG Thumbnail
```

saves the cover image directly to the download folder.

JPG or WebP thumbnails are automatically converted to **PNG** when required.

---

### 📡 Stream Capture

Universal Downloader includes a dedicated **Stream Capture** mode for compatible, non-DRM media.

Use cases:

- Live video streams
- Web radios
- Direct audio streams
- HLS / M3U8
- DASH / MPD
- Partial VOD capture

Available modes:

```text
Video + Audio
Audio only
```

For on-demand media (VOD), you can define:

- Start time
- Duration

Examples:

```text
01:12:30
12:30
90
```

For live streams, recording starts as soon as you click the record button.

> Universal Downloader is not designed to bypass DRM or proprietary encrypted streams.

---

### 🔗 Direct Stream Support

Universal Downloader detects and processes raw media URLs directly, bypassing site-specific extractors.

Examples:

```text
[https://example.com/audio.mp3](https://example.com/audio.mp3)
[https://example.com/live.m3u8](https://example.com/live.m3u8)
[https://example.com/stream.mpd](https://example.com/stream.mpd)
```

Typical supported formats:

```text
MP3
AAC
M4A
OGG
OPUS
WAV
FLAC
M3U8
MPD
```

**FFprobe** analyzes the stream metadata while **FFmpeg** handles recording and transcoding.

---

### 📋 Download Queue

The right-hand panel manages active and queued downloads.

Features:

- Multi-item queuing
- Sequential processing
- Real-time progress updates
- Pause / Resume queue
- Remove pending items
- Cancel current download
- Stop and clear entire queue
- Detailed live activity log

---

### 📊 Local History

Universal Downloader keeps a persistent record of completed downloads.

Stored metadata:

- Title
- Platform
- File size
- Date & time
- Source URL
- Local file path

Actions available from the history tab:

- **▶ Open file**
- **📁 Reveal in folder**
- **URL Copy source URL**
- **× Delete file**

History logging can be disabled in the application settings.

---

### 🔄 Built-in yt-dlp Updater

Universal Downloader can update **yt-dlp directly from within the app**.

Two release channels are supported:

```text
Stable
Nightly
```

#### Stable

Recommended for general use.

#### Nightly

Receives extractor patches faster whenever platforms like YouTube or Vimeo update their systems.

> Only **yt-dlp** is updated from within the app.  
> Universal Downloader itself is updated manually via GitHub Releases.

---

### 🧰 Built-in Diagnostics

The **Diagnostics** panel checks the presence and versions of all embedded binaries:

```text
yt-dlp
FFmpeg
FFprobe
Deno
```

This makes troubleshooting local execution or binary issues fast and straightforward.

---

## 🧠 MCP / AI Local

Universal Downloader v2 can expose a controlled local MCP interface for **Codex** and other compatible MCP clients.

Typical actions include:

```text
Analyze a media URL
Download with a predefined profile
Download a thumbnail
Capture a compatible stream
Read queue status
Read local history
Run diagnostics
```

The application includes a **Copy Codex config** button to simplify local setup.

MCP access is disabled until explicitly enabled in Universal Downloader. AI clients interact through predefined tools rather than unrestricted system commands.

### Controlled automation

Universal Downloader does not expose a generic shell such as `run_command`, `exec` or arbitrary filesystem execution.

This keeps the AI layer focused on Universal Downloader operations instead of granting broad access to the computer.

---

## 🦙 Local Ollama Assistant

Universal Downloader can also be driven by an **Ollama model running locally on your PC**.

The app connects only to a local Ollama endpoint such as:

```text
http://127.0.0.1:11434
```

Main capabilities:

- Natural-language media analysis
- Video/audio downloads through profiles
- Batch downloads from multiple URLs
- Thumbnail downloads
- Compatible stream capture
- Queue and history queries
- Built-in diagnostics
- Tool-call activity displayed in real time

A tool-calling capable Ollama model is required. **Gemma4 12B Q4_K_M** has been tested successfully with the v2 workflow.

> Ollama is optional and is **not bundled** with Universal Downloader. It must be installed and running separately if you want to use the local AI assistant.

### Ollama permissions

The user can explicitly allow or deny download/capture actions. Ollama is not given access to:

- arbitrary shell commands
- arbitrary filesystem browsing
- file deletion
- yt-dlp updates

---

## 📄 Secure URL List Import

The local assistant can work with URL lists selected by the user.

Supported formats:

```text
.txt
.md
.csv
```

Universal Downloader extracts HTTP/HTTPS URLs from the selected file and can queue them using natural-language instructions such as:

```text
Download all URLs from this file in 1080p.
```

or:

```text
Download all URLs from this file as MP3 320 kbps.
```

The file importer is deliberately restricted and does not provide the model with unrestricted filesystem access.

---

## 🔒 YouTube Privacy Mode

Universal Downloader features a **YouTube Privacy Mode**, enabled by default.

When active, the following are ignored for YouTube requests:

- Browser cookies
- `cookies.txt`
- Custom User-Agent
- Chrome impersonation

The objective is to avoid binding downloads to an authenticated Google account unnecessarily.

> This mode does not provide complete anonymity.  
> Your IP address remains visible to remote hosts.

---

## 🔐 Protected Sites / Session Options

Certain websites or restricted contents require an authenticated user session.

Universal Downloader supports:

```text
None
Firefox
Chrome
Edge
Brave
cookies.txt
```

### Browser Cookies

Cookies can be required for:

- Private or unlisted videos
- Account-restricted content
- Age-restricted media
- Platforms enforcing an active session

For public content, Universal Downloader defaults to standard anonymous requests.

If the Chrome / Edge / Firefox cookie store is locked, the application can automatically fall back to **no cookies** when anonymous extraction is possible.

---

### User-Agent

The **User-Agent** input lets you manually pass a custom HTTP identification string.

Example:

```text
Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...
```

For most use cases, it is recommended to leave this field empty.

---

### Chrome Impersonation

The **Chrome Impersonation** toggle instructs the underlying engine to mimic the network fingerprint of a standard Chrome desktop browser.

This can help bypass specific bot detection challenges or CDN blocks.

Standard configuration:

```text
User-Agent: Empty
Chrome Impersonation: Disabled
```

Enable only if a platform rejects standard extraction calls.

---

## 🎞️ Vimeo

Vimeo often requires an authenticated session for private, domain-restricted, or password-protected videos.

If anonymous extraction fails:

1. Log into Vimeo via Firefox, Chrome, Edge, or Brave.
2. Open **Protected Sites / Session Options**.
3. Select the browser you logged in with.
4. Retry the analysis.

If the browser's cookie database is locked, close the web browser entirely and try again.

---

## 🌍 Supported Platforms

Universal Downloader is built around **yt-dlp**.

Subject to the extractors included in the current yt-dlp release, the app supports hundreds of platforms, including:

- YouTube
- Vimeo
- Dailymotion
- Facebook
- Instagram
- TikTok
- Twitter / X
- Twitch
- Reddit
- And many others

> Platform compatibility can change over time.  
> Use the built-in yt-dlp update tool to pull downstream extractor fixes as soon as they are published.

---

## 📦 Portable Edition

Universal Downloader is distributed as a **portable Windows x64 ZIP archive**.

### No Installer Required

Simply download the archive, extract it anywhere, and execute:

```text
UniversalDownloader.exe
```

No system registry modifications or installation wizards.

---

## ✅ Zero External Dependencies for Core Downloading

The portable bundle ships with the runtime requirements needed for Universal Downloader itself.

You do **not** need to install:

```text
Python
Node.js
npm
FFmpeg
FFprobe
Deno
yt-dlp
```

All core engines are embedded and pre-configured.

**Ollama is the only optional external component**: install it separately only if you want to use the local AI assistant.

---

## 📖 Quick Start Guide

### 1. Download and Launch

1. Download the latest release from the GitHub **Releases** page.
2. Extract the ZIP archive completely.
3. Open the extracted folder.
4. Launch:

```text
UniversalDownloader.exe
```

> Ensure the extracted folder is placed in a directory with standard write permissions.

---

### 2. Downloading a Video

```text
1. Paste the URL
2. Click Parse
3. Check the title and thumbnail preview
4. Select a preset profile or manual stream
5. Click Download
```

The task will be queued and processed automatically.

---

### 3. Extracting Audio Only

```text
1. Parse the media URL
2. Choose MP3 192 kbps or MP3 320 kbps preset

or

3. Open the MP3 Audio tab
4. Select the desired audio track
5. Click Download
```

---

### 4. Downloading Cover Art

Once parsed:

```text
Download PNG Thumbnail
```

The resulting PNG image is placed directly into the `UD_download` folder.

---

### 5. Capturing Live Streams

```text
1. Paste the live stream URL
2. Click Parse
3. Open Stream Capture
4. Choose Video + Audio or Audio only
5. Click Start Capture
6. Stop and finalize the recording when done
```

---

### 6. Using Codex via MCP

```text
1. Enable MCP / Local AI in Universal Downloader
2. Click Copy Codex config
3. Add the generated configuration to Codex
4. Restart/reload Codex if required
5. Ask Codex to analyze or download media through Universal Downloader
```

Example:

```text
Analyze this URL with Universal Downloader, then download it as MP3 320 kbps.
```

---

### 7. Using the Local Ollama Assistant

```text
1. Start Ollama on the PC
2. Enable the Ollama assistant in Universal Downloader
3. Keep the default local server: http://127.0.0.1:11434
4. Click Refresh and choose a tool-calling compatible model
5. Optionally allow download/capture actions
6. Enter a natural-language instruction in the assistant panel
```

Example:

```text
Download these videos in 1080p and also save their thumbnails.
```

---

### 8. Importing a URL List

Use **URL File** in the Ollama panel to select a `.txt`, `.md` or `.csv` file.

Example file:

```text
https://www.youtube.com/watch?v=example1
https://vimeo.com/example2
https://www.youtube.com/shorts/example3
```

Then ask:

```text
Download all links from this file at maximum quality.
```

---

## 📁 Portable Directory Layout

The application operates within its self-contained directory:

```text
UniversalDownloader/
├── UniversalDownloader.exe
├── resources/
│   ├── bin/
│   └── mcp/
├── UD_download/
└── UD_data/
```

### `UD_download`

Default destination directory for:

- Videos
- Extracted audio tracks
- Stream recordings
- Cover thumbnails

By default, it is generated **next to the executable**.

If the portable folder is moved to another drive, the download folder follows automatically. You can also pick a custom path from the settings.

---

### `UD_data`

Contains user configurations and persistent local data:

```text
settings.json
download_history.json
```

This self-contained structure ensures real portability without leaving files behind in user directories.

---

## 🖼️ Screenshots

You can store your screenshots in:

```text
docs/screenshots/
```

Reference them in Markdown like this:

```markdown
![Main Interface](docs/screenshots/main-interface.png)

![Download Presets](docs/screenshots/download-profiles.png)

![Stream Capture](docs/screenshots/stream-capture.png)

![History](docs/screenshots/history.png)
```

<!--
GitHub user-attachments format:

<img width="1600" alt="Universal Downloader" src="https://github.com/user-attachments/assets/YOUR-ID" />
-->

---

## 🔐 Electron Security Architecture

Universal Downloader strictly isolates the user interface from the system runtime.

```text
Renderer HTML / CSS / JS
          ↓
      preload.js
          ↓
     Strict IPC
          ↓
      main.js
       ↙     ↘
 Core media   Controlled AI bridge
    ↓              ↓
yt-dlp / FFmpeg   MCP / Ollama tools
```

The renderer process does not have arbitrary Node.js access.

Electron security baseline:

```text
nodeIntegration: false
contextIsolation: true
```

External binaries are invoked using sanitized argument arrays, avoiding unsanitized command shell executions.

---

### Cookies Notice

Only load browser cookies when content cannot be retrieved anonymously.

For standard public content:

```text
Cookies: None
```

remains the safest and fastest option.

---

### Disk Space

Media downloads can quickly saturate storage drives.

Default storage directory:

```text
UD_download
```

Consider moving completed archives to long-term storage periodically.

---

## ⚠️ Known Limitations

Universal Downloader relies on external web infrastructure.

Third-party platforms regularly update:

- Video players
- Internal APIs
- Anti-bot heuristics
- Authentication protocols
- Delivery formats
- CDN setups

A service functional today may require a patched version of yt-dlp tomorrow. Permanent or uninterrupted compatibility with any specific platform cannot be guaranteed.

---

## ⚖️ Legal Disclaimer

This utility is provided for personal archiving, legal backup, educational, and authorized media acquisition purposes only.

Users are solely responsible for ensuring they hold the explicit right or authorization to download or record any target media.

Always comply with:

- Local copyright laws and intellectual property regulations
- Creators' rights and applicable distribution licenses
- Terms of Service governing third-party host platforms

The developer accepts no liability for misuse, illicit distribution, or copyright infringement committed with this software.

Universal Downloader is neither engineered nor intended to circumvent DRM systems, digital rights encryption, or paywalled access controls.

---

## 🔧 Core Technologies

Universal Downloader is built with:

- **Electron** — Cross-platform desktop runtime
- **yt-dlp** — Core media scraping and extraction engine
- **FFmpeg** — Stream processing, remuxing, and audio transcoding
- **FFprobe** — Media analysis and stream inspection
- **Deno** — Lightweight JavaScript runtime used by select yt-dlp extractors
- **Model Context Protocol (MCP)** — Controlled integration with Codex and compatible AI clients
- **Ollama API** — Optional local model integration and tool calling

All third-party modules and binaries remain under their respective licenses.

---

## 📝 Credits

- **yt-dlp** — https://github.com/yt-dlp/yt-dlp
- **Electron** — https://www.electronjs.org/
- **FFmpeg** — https://ffmpeg.org/
- **Deno** — https://deno.com/
- **Model Context Protocol** — https://modelcontextprotocol.io/
- **Ollama** — https://ollama.com/

---

<div align="center">

### 🌟 Show Your Support

If this project helped you, please consider giving it a ⭐ on GitHub!

**by Orion4D**

<a href="https://ko-fi.com/orion4d">
<img src="https://ko-fi.com/img/githubbutton_sm.svg" alt="Buy Me A Coffee" height="41" width="174">
</a>

</div>

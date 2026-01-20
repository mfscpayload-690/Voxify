# Voxify

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-6366f1?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-22c55e?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Web-0ea5e9?style=flat-square)

**Real-time Speech Fluency Analyzer with AI-Powered Coaching**

[Features](#features) · [Quick Start](#quick-start) · [Configuration](#configuration) · [Documentation](#documentation)

</div>

---

## Overview

**Voxify** is a browser-based speech fluency analysis tool that provides real-time feedback on speaking patterns. It detects filler words, stammers, and pacing issues while offering personalized coaching through an integrated AI assistant.

All processing happens locally in your browser — *no audio data is sent to external servers*.

---

## Features

### Speech Analysis
- **Real-time Transcription** — Powered by the Web Speech API
- **Filler Word Detection** — Identifies "um", "uh", "like", "you know", etc.
- **Stammer Recognition** — Detects repeated syllables and word fragments
- **Pause Monitoring** — Tracks extended silences (>1.5 seconds)

### Visual Feedback
- **Waveform Visualization** — Live audio waveform display
- **Frequency Spectrum** — Real-time audio frequency bars
- **Volume Meter** — Monitor speaking volume levels
- **Highlighted Transcript** — Visual marking of detected patterns

### Fluency Scoring
- **0–100 Score System** — Comprehensive fluency rating
- **Grade Classification** — Excellent, Good, Moderate, Needs Work
- **Age-Based Baselines** — Fair comparison across age groups
- **Component Breakdown** — Detailed metric analysis

### AI Coaching *(Optional)*
- **Personalized Feedback** — Context-aware suggestions
- **Session Summaries** — Analysis upon completion
- **Improvement Tips** — Actionable recommendations

---

## Quick Start

### Prerequisites

- **Google Chrome** or **Microsoft Edge** (recommended)
- Microphone access
- *(Optional)* [Ollama](https://ollama.ai/) for AI coaching features

### Installation

```bash
# Clone the repository
git clone https://github.com/mfscpayload-690/voxify.git
cd voxify

# Create your configuration file
cp config.example.js config.js
```

### Running the Application

> **Note:** The application must be served via HTTP for full functionality. Direct file access (`file://`) will limit AI features.

```bash
# Start a local development server
npx http-server . -p 8080

# Open in your browser
# Navigate to: http://localhost:8080
```

### Enabling AI Coaching *(Optional)*

1. **Install Ollama** from [ollama.ai](https://ollama.ai/)

2. **Start Ollama with CORS enabled:**

   ```bash
   # Windows (PowerShell)
   $env:OLLAMA_ORIGINS="*"; ollama serve

   # macOS / Linux
   OLLAMA_ORIGINS="*" ollama serve
   ```

3. **Download the language model:**

   ```bash
   ollama pull qwen2.5-coder:7b-instruct-q4_K_M
   ```

---

## Configuration

Configuration is managed through `config.js`. Copy from the example and modify as needed:

```javascript
const CONFIG = {
    // Ollama API endpoint
    OLLAMA_URL: 'http://localhost:11434',
    
    // Language model for AI coaching
    OLLAMA_MODEL: 'qwen2.5-coder:7b-instruct-q4_K_M',
    
    // AI feedback interval (milliseconds)
    AI_FEEDBACK_INTERVAL: 5000,
    
    // Minimum word count before AI analysis triggers
    MIN_WORDS_FOR_AI: 10
};
```

---

## Documentation

### Fluency Score Components

| Component     | Weight | Description                        |
| ------------- | ------ | ---------------------------------- |
| Filler Words  | 30%    | Frequency of verbal fillers        |
| Stammers      | 25%    | Repeated syllables or words        |
| Speaking Pace | 25%    | Words per minute vs. optimal range |
| Silence Ratio | 20%    | Proportion of silent time          |

### Score Interpretation

| Score  | Grade      | Interpretation          |
| ------ | ---------- | ----------------------- |
| 85–100 | Excellent  | Outstanding fluency     |
| 70–84  | Good       | Clear, confident speech |
| 50–69  | Moderate   | Room for improvement    |
| 0–49   | Needs Work | Practice recommended    |

### Age-Based Baselines

| Age Group | Optimal WPM | Expected Fillers | Silence Ratio |
| --------- | ----------- | ---------------- | ------------- |
| 6–8       | 80–120      | ≤6               | ≤25%          |
| 9–11      | 100–140     | ≤4               | ≤20%          |
| 12–14     | 120–160     | ≤3               | ≤15%          |
| 15+       | 130–170     | ≤2               | ≤12%          |

### Metrics Reference

| Metric      | Description                          |
| ----------- | ------------------------------------ |
| Words/Min   | Speaking pace (optimal: 120–150 WPM) |
| Fillers     | Total detected filler words          |
| Stammers    | Repeated syllables or fragments      |
| Long Pauses | Silences exceeding 1.5 seconds       |
| Silence %   | Percentage of total time in silence  |
| Word Count  | Total transcribed words              |

---

## Technology Stack

| Component      | Technology                                                                        |
| -------------- | --------------------------------------------------------------------------------- |
| Transcription  | [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) |
| Audio Analysis | [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)   |
| Visualization  | Canvas API                                                                        |
| AI Integration | [Ollama](https://ollama.ai/) (local LLM)                                          |
| UI Framework   | Vanilla JavaScript, CSS3                                                          |
| Typography     | [Inter](https://fonts.google.com/specimen/Inter)                                  |
| Icons          | [Lucide](https://lucide.dev/)                                                     |

---

## Browser Compatibility

| Browser         | Support Level        |
| --------------- | -------------------- |
| Google Chrome   | Full *(recommended)* |
| Microsoft Edge  | Full                 |
| Mozilla Firefox | Partial              |
| Apple Safari    | Partial              |

> Web Speech API provides the best experience in Chromium-based browsers.

---

## Use Cases

- **Public Speaking** — Reduce filler words before presentations
- **Interview Preparation** — Practice clear, confident responses
- **Language Learning** — Track fluency improvement over time
- **Speech Therapy** — Monitor and measure progress
- **Education** — Help students develop speaking skills

---

## Disclaimer

> This application is intended for **educational and practice purposes only**. Speech analysis accuracy depends on browser capabilities, microphone quality, and environmental factors. **Not intended for clinical or diagnostic use.**

---

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

<div align="center">

**[Report an Issue](https://github.com/mfscpayload-690/voxify/issues)** · **[Request a Feature](https://github.com/mfscpayload-690/voxify/issues)**

</div>

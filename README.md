# FluentFlow

<div align="center">

![FluentFlow Logo](https://img.shields.io/badge/🎤-FluentFlow-f59e0b?style=for-the-badge)
![Version](https://img.shields.io/badge/version-1.0-blue?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Demo](https://img.shields.io/badge/demo-live-brightgreen?style=flat-square)

**Real-time Speech Fluency Analysis • Pattern Detection • AI-Powered Coaching**

[Features](#-features) • [Quick Start](#-quick-start) • [Fluency Score](#-fluency-scoring) • [Configuration](#️-configuration)

</div>

---

## ✨ Features

### 🎤 Live Speech Capture
- **Real-time Transcription** — Powered by Web Speech API
- **Waveform Visualization** — See your audio in real-time
- **Frequency Bars** — Visual audio spectrum display
- **Volume Monitoring** — Track your speaking volume

### 📝 Pattern Detection
- **Filler Word Detection** — Catches "um", "uh", "like", "you know", etc.
- **Stammer Recognition** — Identifies repeated syllables
- **Pause Analysis** — Monitors long silences
- **Highlighted Transcript** — Visual pattern marking

### 📊 Fluency Scoring
- **0-100 Score System** — Comprehensive fluency rating
- **Grade Classification** — Excellent, Good, Moderate, Needs Work
- **Age-Based Baselines** — Fair comparison across age groups
- **Component Breakdown** — See what affects your score

### ⚡ Pace Coaching
- **Real-time WPM Tracking** — Words per minute display
- **Optimal Range Indicator** — Visual pace feedback
- **Speed Advice** — Too slow? Too fast? Get feedback
- **Age-Adjusted Targets** — Appropriate goals for each group

### 🤖 AI Speech Coach
- **Personalized Feedback** — Based on your specific patterns
- **Encouraging Tone** — Constructive, supportive advice
- **Improvement Tips** — Actionable suggestions
- **Session Summaries** — Final analysis when you stop

---

## 🚀 Quick Start

### Prerequisites
- **Google Chrome** (recommended) — Best Web Speech API support
- Microphone access
- (Optional) [Ollama](https://ollama.ai/) for AI coaching

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/fluentflow.git
cd fluentflow

# Open in Chrome
start index.html  # Windows
open -a "Google Chrome" index.html  # macOS
google-chrome index.html  # Linux
```

### With Local Server (Recommended for HTTPS)
```bash
npx http-server . -p 8080 --ssl
```

### Enable AI Coaching (Optional)
```bash
ollama run qwen2.5-coder:7b-instruct-q4_K_M
```

---

## 📊 Fluency Scoring

### Score Components

| Component | Weight | What It Measures |
|-----------|--------|------------------|
| Filler Words | 30% | Frequency of "um", "uh", etc. |
| Stammers | 25% | Repeated syllables/words |
| Speaking Pace | 25% | Words per minute vs optimal |
| Silence Ratio | 20% | Proportion of quiet time |

### Score Grades

| Score | Grade | Description |
|-------|-------|-------------|
| 85-100 | 🌟 Excellent | Outstanding fluency |
| 70-84 | ✅ Good | Solid, clear speech |
| 50-69 | ⚠️ Moderate | Room for improvement |
| 0-49 | 📝 Needs Work | Practice recommended |

### Age-Based Baselines

| Age Group | Optimal WPM | Expected Fillers | Silence Ratio |
|-----------|-------------|------------------|---------------|
| 6-8 | 80-120 | 6 | 25% |
| 9-11 | 100-140 | 4 | 20% |
| 12-14 | 120-160 | 3 | 15% |
| 15+ | 130-170 | 2 | 12% |

---

## 📊 Metrics Explained

| Metric | Description |
|--------|-------------|
| **Words/Min** | Speaking pace (target: 120-150 for adults) |
| **Fillers** | Count of detected filler words |
| **Stammers** | Repeated syllables or word fragments |
| **Long Pauses** | Silences over 1.5 seconds |
| **Silence %** | Percentage of recording in silence |
| **Word Count** | Total words transcribed |

---

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| Transcription | Web Speech API |
| Audio | Web Audio API |
| Visualization | Canvas API |
| AI Coaching | [Ollama](https://ollama.ai/) |
| UI | Vanilla JavaScript + CSS3 |
| Fonts | [Inter](https://fonts.google.com/specimen/Inter) |

---

## ⚙️ Configuration

```javascript
// AI Settings
const OLLAMA_URL = 'http://localhost:11434';
const MODEL = 'qwen2.5-coder:7b-instruct-q4_K_M';
const AI_INTERVAL = 5000;  // Feedback frequency (ms)

// Filler Words (customize as needed)
const FILLER_WORDS = [
  'um', 'uh', 'er', 'ah', 'like', 
  'you know', 'basically', 'actually',
  'literally', 'so', 'well', 'i mean'
];
```

---

## 🌐 Browser Support

| Browser | Support |
|---------|---------|
| Chrome | ✅ Full (recommended) |
| Edge | ✅ Full |
| Firefox | ⚠️ Limited |
| Safari | ⚠️ Limited |

> **Note:** Web Speech API works best in Chrome and Edge.

---

## 🎯 Use Cases

- **Public Speaking Practice** — Reduce fillers before presentations
- **Language Learning** — Track fluency development
- **Speech Therapy Support** — Monitor progress
- **Interview Prep** — Polish your verbal communication
- **Classroom Learning** — Help students improve

---

## 💡 Quick Tips

1. **Replace fillers with pauses** — Silence is more powerful than "um"
2. **Aim for 120-150 WPM** — Optimal pace for clarity
3. **Take a breath** — Before complex sentences
4. **Practice regularly** — Fluency improves with practice
5. **Record and review** — Listen to your patterns

---

## ⚠️ Disclaimer

> **Demo Only** — Speech analysis uses browser APIs and may vary by browser, device, and environment. This tool is NOT for clinical assessment. All processing happens locally — no audio is sent to external servers.

---

## 📄 License

MIT License — See [LICENSE](LICENSE) for details.

---

<div align="center">

**Made with ❤️ for the open-source community**

[Report Bug](../../issues) • [Request Feature](../../issues)

</div>

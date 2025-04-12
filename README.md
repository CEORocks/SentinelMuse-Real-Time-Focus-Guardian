```markdown
# 👁️‍🗨️ SentinelMuse: Real-Time Focus Guardian

SentinelMuse is not just a productivity app — it’s your digital muse with a purpose. It keeps watch over your screen using visual-language AI, understands your defined task goals, and helps you avoid slipping into distraction without relying on rigid blockers.

Built with a balance of psychology, tech, and a dash of wit, SentinelMuse adapts to how you work, then gently — or not so gently — brings your attention back when it notices you slipping.

<p align="center">
  <img src="./assets/sentinelmuse-demo.gif" alt="SentinelMuse in action" width="420">
</p>

## 🧠 Project Overview

Unlike blunt blockers or timers, SentinelMuse leverages AI vision to intelligently *understand* your screen. You start by telling it what you’re working on, what’s allowed, and what’s off-limits. It watches your screen via lightweight screenshots and uses a multimodal model to analyze your behavior in real time.

When distraction is detected, it jumps in with a nudge — anything from a motivational whisper to a full-screen intervention. You're in control of the tone.

It's smart enough to know that watching a lecture counts — but bingeing old episodes of something probably doesn't.

## 🔑 Core Features

- **Vision-Aware Monitoring**: Understands screen context, not just URLs or apps.
- **Intent-Based Sessions**: Define what your focus looks like — SentinelMuse holds you to it.
- **Voice Personality System**: Select tone and voice for nudges — calm mentor or snarky coach.
- **Live Interventions**: Screen fade, countdowns, and voice reminders that activate upon distraction.
- **Model Switching**: Two-tier system with local LLaVA or Gemini Nano as the router, GPT-4 or Claude as the heavy lifter.
- **Modular Alerts**: Choose how disruptive you want SentinelMuse to be when it catches you slipping.
- **Focus Logs**: Track violations, session notes, and reflection prompts post-session.

## ⚙️ Installation

> **Supported on macOS. Windows support coming via the `win-port` branch.**

```bash
git clone https://github.com/yourusername/sentinelmuse.git
cd sentinelmuse
python -m venv museenv
source museenv/bin/activate
pip install -r requirements.txt
./launch.sh
```

- You may need to approve screen recording permissions during setup.

## 🔧 API Keys Setup

You'll need the following API keys in your environment:

```plaintext
OPENAI_API_KEY=sk-xxxx
ANTHROPIC_API_KEY=sk-xxxx
GEMINI_API_KEY=your_google_ai_key
ELEVEN_LABS_API_KEY=your_voice_key
```

For two-tier mode with local inference:
- Install [Ollama](https://ollama.com)
- Pull the local model:
```bash
ollama pull llava
```

Ensure Ollama is running before launch if using local routing.

## 🛠️ Configurable Parameters

| Option           | Description |
|------------------|-------------|
| `model_name`     | Name of the main model (e.g. gpt-4, claude-sonnet) |
| `router_model`   | Lightweight model for pre-screening |
| `two_tier`       | Enable smart cost-saving routing |
| `voice`          | Choose the TTS voice style |
| `tone`           | Set personality: calm, direct, sarcastic, inspiring |
| `delay_interval` | Time between screen captures |
| `session_goals`  | Describe your task for contextual accuracy |
| `countdown_secs` | How long to comply before escalation |
| `mute_mode`      | Mutes music/apps when alerts fire |
| `debug_mode`     | Print raw reasoning from the model |

## 🚦 How SentinelMuse Works

1. You declare your focus intention and define what’s okay or not okay.
2. SentinelMuse captures screenshots discreetly at intervals.
3. Screens are processed through your selected AI stack to interpret intent vs. current behavior.
4. When distraction is flagged, it:
   - Displays a visual alert
   - Plays a voice nudge
   - Triggers a timed warning for you to comply

If ignored, it repeats until behavior realigns or session is paused.

## 🗂️ File Structure Overview

- `sentinel.py`: main logic, monitoring loop, model calls
- `interface.py`: GUI built with PySide6
- `models.py`: handles calls to multimodal models
- `alert_engine.py`: manages on-screen interventions and TTS
- `prompts.yaml`: fine-tuned prompts and templates
- `session_state.json`: live session config and metrics

## 🧭 Roadmap

- Adaptive session guidance via short-term memory
- Emotion detection based on posture (via webcam, opt-in)
- Real-time music muting during alerts
- Post-session reflection journal
- Slack/Discord plugin for “focus sync” groups
- Enforced "deep mode" with custom task locks

## 👥 Contributors

- [@yourusername](https://github.com/yourusername) — Creator & Lead Engineer  
- [@collab-dev](https://github.com/collab-dev) — UX & TTS Integration  

## 📜 License

Distributed under the MIT License. See `LICENSE` for full terms.

## 📚 Learn More

Want to understand how AI can nudge you into a flow state without forcing it?

Read our deep-dive:  
[SentinelMuse: Designing a Digital Coach for Mindful Focus](https://medium.com/@yourusername/sentinelmuse-ai-article)

---

**Muse mode on. Distraction off. You’ve got this.**
```


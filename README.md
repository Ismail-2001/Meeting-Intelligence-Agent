# Meeting Intelligence Agentic Platform 🚀

A modular, multi-agent AI system designed to transform raw business conversations into high-impact actionable intelligence. By leveraging specialized AI agents and a meta-intelligence orchestration layer, this platform automates the extraction of decisions, sales qualification (MEDDIC/BANT), and workflow optimization from meeting and sales call transcripts.

---

## 🌟 Key Features

- **Multi-Agent Orchestrator**: An intelligent conductor that analyzes user requests to determine the optimal execution path and synthesizes insights from multiple specialized agents.
- **Meeting Intelligence Agent**: Extracts C-suite executive summaries, specific action items with importance weighting, and key organizational decisions.
- **Sales Intelligence Agent**: Real-time sales call analysis using **MEDDIC** and **BANT** frameworks, deal health scoring (0-100), and "Next Best Action" recommendations to accelerate revenue.
- **Workflow Automation Agent**: Analyzes manual processes and generates production-ready automation specifications, Python code, and ROI projections.
- **Provider Agnostic**: Seamless support for **DeepSeek**, **Kimi (Moonshot AI)**, **Anthropic (Claude)**, and **OpenAI** via a unified LLM client.
- **Structured JSON Outputs**: All intelligence is delivered in strict, machine-readable JSON formats for easy integration with CRMs or internal tools.

---

## 🛠 Tech Stack

- **Backend**: Python 3.10+
- **AI Orchestration**: Custom Agentic Framework (Planning -> Execution -> Synthesis)
- **LLM Support**: 
  - DeepSeek (deepseek-chat)
  - Moonshot AI (kimi-v1)
  - Anthropic (Claude 3.5 Sonnet)
  - OpenAI (GPT-4o)
- **Libraries**: `openai`, `anthropic`, `python-dotenv`, `pydantic`, `pytest`
- **Infrastructure**: CLI-based (expandable to FastAPI/Docker)

---

## 📂 Architecture

The platform follows a modular **Planner-Executor-Synthesizer** pattern:

1.  **Request Analysis**: The Orchestrator evaluates the user's intent.
2.  **Agent Routing**: Parallel or sequential routing to specialized agents (Meeting, Sales, or Workflow).
3.  **Specialized Analysis**: Agents process content using domain-specific expert system prompts.
4.  **Meta-Synthesis**: The Orchestrator merges agent outputs into a unified, cross-functional response.

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.10 or higher
- API tokens for DeepSeek, Moonshot, or Anthropic

### Local Setup
1. **Clone the repository**
   ```bash
   git clone https://github.com/Ismail-2001/Meeting-Intelligence-Agent.git
   cd Meeting-Intelligence-Agent
   ```

2. **Setup virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: .\venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables**
   Create a `.env` file in the root directory:
   ```env
   # Choose your provider
   DEEPSEEK_API_KEY=your_key_here
   OPENAI_BASE_URL=https://api.deepseek.com
   
   # Optional: Others
   ANTHROPIC_API_KEY=your_key_here
   KIMI_API_KEY=your_key_here
   ```

---

## 📖 Usage

Run the platform via the CLI agentic interface:

### Analyze a Meeting Transcript
```bash
python src/main.py --request "Summarize this meeting and extract action items" --file transcripts/sync_meeting.txt --provider openai
```

### Sales Intelligence (MEDDIC)
```bash
python src/main.py --request "Analyze this call for MEDDIC qualification" --text "Rep: Hi... John: Our budget is $50k..." --provider openai
```

### Automation Generation
```bash
python src/main.py --request "Design an automation for this" --text "We manually copy emails to sheets every Monday." --provider openai
```

---

## 🚢 Deployment

### Docker (Recommended)
You can containerize this platform for cloud deployment:
```bash
docker build -t meeting-intel-agent .
docker run --env-file .env meeting-intel-agent
```

---

## 🗺 Roadmap
- [ ] **Web UI**: Next.js dashboard for visual interaction.
- [ ] **CRM Integration**: Direct sync with HubSpot and Salesforce.
- [ ] **Context Memory**: Support for referencing previous meetings in a series.
- [ ] **Voice Support**: Direct processing of audio files (MP3/WAV) using Whisper.

---

## 🤝 Contributing

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---
Created with ❤️ by [Ismail](https://github.com/Ismail-2001)

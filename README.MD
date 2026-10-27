# 🤖 AI Agents Using Agno

A collection of AI-powered agents built with the [Agno](https://github.com/agno-agi/agno) framework. This repository demonstrates three distinct agent patterns: **financial analysis**, **multi-language team collaboration**, and **YouTube video analysis** with a Streamlit UI.

## 📋 Agents Overview

| Agent | File | Description |
|-------|------|-------------|
| 💰 **Finance Agent** | `finance_agent.py` | Investment analyst that researches stock prices, analyst recommendations, and fundamentals using YFinance + DuckDuckGo tools |
| 🌐 **Answer & Translation Team** | `Answer_Translation_Team.py` | Multi-agent team that answers a query in English, Chinese, and Hindi simultaneously |
| 🎥 **YouTube Analyzer** | `youtube_analyzer/` | Expert YouTube content analyst that generates detailed timestamped reports |
| 🖥️ **Streamlit UI** | `youtube_analyzer/StreamLit_ui.py` | Interactive web interface for the YouTube Analyzer |

## 🚀 Quick Start

### 1. Clone the Repository

    git clone https://github.com/shivgupta-iitp/Ai_Agents_Using_Agno.git
    cd Ai_Agents_Using_Agno

### 2. Create a Virtual Environment

    python -m venv .venv

Activate it:

    source .venv/bin/activate      # Linux / macOS
    .venv\Scripts\activate         # Windows

### 3. Install Dependencies

    pip install -r requirements.txt

If `requirements.txt` is missing, install manually:

    pip install agno streamlit python-dotenv duckduckgo-search yfinance

### 4. Configure API Keys

Create a `.env` file in the project root with the following content:

    # Required for YouTube Analyzer (OpenAI)
    OPENAI_API_KEY=your_openai_api_key_here

    # Required for Finance Agent & Translation Team (Groq)
    GROQ_API_KEY=your_groq_api_key_here

Get your keys from:
- 🔑 [OpenAI Platform](https://platform.openai.com/api-keys)
- 🔑 [Groq Console](https://console.groq.com/keys)

## 🎯 Usage

### 💰 Finance Agent

Researches stock prices, analyst recommendations, and fundamentals.

    python finance_agent.py

Default query: *"Share the MSFT stock price and analyst recommendations."*
Edit the `print_response(...)` call at the bottom to query other tickers.

---

### 🌐 Answer & Translation Team

Sends the same question to three language-specific agents (English, Chinese, Hindi) and returns all responses.

    python Answer_Translation_Team.py

Default query: *"What is the capital of India?"*

---

### 🎥 YouTube Analyzer (CLI)

Analyzes a YouTube video and produces a structured report with timestamps, topics, and key moments.

    python youtube_analyzer.py

Edit the video URL in the `print_response(...)` call at the bottom.

---

### 🖥️ YouTube Analyzer (Streamlit UI)

Launch the interactive web app:

    streamlit run youtube_analyzer/StreamLit_ui.py

Then open `http://localhost:8501` and paste any YouTube link.

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Agent Framework | [Agno](https://github.com/agno-agi/agno) |
| LLM Providers | [Groq](https://groq.com/) (Qwen 3 32B), [OpenAI](https://openai.com/) |
| Data Tools | [YFinance](https://github.com/ranaroussi/yfinance), DuckDuckGo, YouTubeTools |
| Frontend | [Streamlit](https://streamlit.io/) |
| Config | [python-dotenv](https://github.com/theskumar/python-dotenv) |

## 📁 Project Structure

    Ai_Agents_Using_Agno/
    │
    ├── finance_agent.py              # Financial analysis agent
    ├── Answer_Translation_Team.py    # Multi-language team agent
    │
    └── youtube_analyzer/
        ├── youtube_analyzer.py       # YouTube analysis agent (CLI)
        └── StreamLit_ui.py           # Streamlit web UI

## ⚠️ Important Notes

- **Never commit your `.env` file.** It contains API keys. Ensure `.env` is in `.gitignore`.
- `finance_agent.py` runs with `debug_mode=True` for development — set to `False` for production.
- Model IDs (e.g., `qwen/qwen3-32b`, `gpt-5.2`) may need updating as providers evolve. Verify against current provider documentation.
- API usage may incur costs — monitor your usage on Groq and OpenAI dashboards.

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/new-agent`)
3. Commit your changes (`git commit -m 'Add new agent'`)
4. Push (`git push origin feature/new-agent`)
5. Open a Pull Request

## 📄 License

This project is open-sourced for learning purposes. See the repository for license details.

## 🔗 Links

- [Agno Documentation](https://docs.agno.com/)
- [Streamlit Documentation](https://docs.streamlit.io/)
- [Groq Models](https://console.groq.com/docs/models)

---

⭐ **If you find this useful, please star the repo!**

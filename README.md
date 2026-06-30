# ResearchMind — Multi-Agent Research Pipeline

🚀 **Live Demo:** https://multi-agent-research-systems.streamlit.app/

An AI-powered research system where four specialized agents collaborate to search the web, scrape content, write a structured report, and critically review it — all from a single topic input.

Built with LangChain, Mistral AI, Tavily Search, and Streamlit.

---

## How It Works

The pipeline runs in 4 sequential steps:

| Step | Agent | Role |
|------|-------|------|
| 01 | Search Agent | Searches the web via Tavily and collects titles, URLs, and snippets |
| 02 | Reader Agent | Picks the most relevant URL and scrapes its full content |
| 03 | Writer Chain | Combines research and writes a structured report using an LLM |
| 04 | Critic Chain | Reviews the report and gives a score, strengths, and areas to improve |

---

## Tech Stack

- **LangChain** — agent orchestration and chain composition
- **Mistral AI** — LLM backend for writing and critiquing
- **Tavily API** — real-time web search
- **BeautifulSoup** — web scraping and content extraction
- **Streamlit** — frontend UI
- **python-dotenv** — environment variable management

---

## Project Structure

```
├── app.py              # Streamlit UI
├── agents.py           # Search agent, Reader agent, Writer chain, Critic chain
├── tools.py            # web_search and scrape_url tools
├── pipeline.py         # Core pipeline logic (CLI entry point)
├── requirements.txt    # Dependencies
└── .env                # API keys (never commit this)
```

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/tahirshamim/multi-agent-research-system.git
cd multi-agent-research-system
```

### 2. Create a virtual environment

```bash
python -m venv .venv
.venv\Scripts\activate      # Windows
source .venv/bin/activate   # Mac/Linux
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the project root:

```
MISTRAL_API_KEY=your-mistral-key-here
TAVILY_API_KEY=your-tavily-key-here
```

Get your keys:
- Mistral → [console.mistral.ai](https://console.mistral.ai)
- Tavily → [app.tavily.com](https://app.tavily.com)

### 5. Run the app

```bash
# Streamlit UI
streamlit run app.py

# Or CLI mode
python pipeline.py
```

---

## Deployment

Deployed on **Streamlit Cloud**. To deploy your own:

1. Push the repo to GitHub (without `.env`)
2. Go to [share.streamlit.io](https://share.streamlit.io)
3. Connect your repo and set main file as `app.py`
4. Add your API keys under **Settings → Secrets**:

```toml
MISTRAL_API_KEY = "your-mistral-key-here"
TAVILY_API_KEY = "your-tavily-key-here"
```

---

## Author

**Tahir Shamim**  
CS Student @ NED University Karachi  
[github.com/tahirshamim](https://github.com/tahirshamim)

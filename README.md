# gemini-adk-first-agent

A minimal [Google Agent Development Kit (ADK)](https://google.github.io/adk-docs/) agent powered by Gemini.

## Project layout

```
.
├── first_agent/
│   ├── __init__.py   # exposes the agent module to ADK
│   ├── agent.py      # defines `root_agent`
│   └── .gitignore    # ignores .env and .adk/
├── requirements.txt
├── LICENSE
└── README.md
```

`first_agent/agent.py` defines `root_agent`, a single LLM agent (`gemini-3.5-flash`) with no tools.

## Prerequisites

- Python 3.10+
- A Gemini API key ([Google AI Studio](https://aistudio.google.com/apikey)) or a Google Cloud project with Vertex AI enabled

## Setup

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Create `first_agent/.env` (git-ignored):

```env
# Google AI Studio
GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=your-api-key

# Or Vertex AI
# GOOGLE_GENAI_USE_VERTEXAI=TRUE
# GOOGLE_CLOUD_PROJECT=your-project-id
# GOOGLE_CLOUD_LOCATION=us-central1
```

## Run

From the repository root:

```bash
adk run first_agent   # interactive CLI
adk web               # web UI; pick `first_agent` in the dropdown
```

## Customize

Edit the `Agent(...)` fields in `first_agent/agent.py` (`model`, `name`, `description`, `instruction`) or add `tools` and sub-agents.

## License

[MIT](LICENSE)

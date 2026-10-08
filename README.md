# Scalable Web AI Agent

A highly scalable, async-first Web AI Agent built with Python and optimized with the [uv package manager](https://docs.astral.sh/uv/). This repository features a production-ready newsletter automation service, dynamic LLM prompt layering, and strong type safety.

## 🗂️ Project Structure

```text
├── .idea/                  # JetBrains / PyCharm configuration
├── .gitignore              # Standard Python and IDE ignore paths
├── .python-version         # Pinned Python version for consistency
├── README.md               # Project documentation (You are here)
├── custom_types.py         # Strongly-typed models, Pydantic schemas, and TypeAliases
├── main.py                 # Core application setup & API router layer
├── newsletter_service.py   # Web agent business logic, scraping, and queue orchestration
├── prompts.py              # LLM system prompts and dynamic templates
├── pyproject.toml          # PEP 621 metadata, tool configs, and dependencies
├── run.py                  # CLI entry point to boot up the agent
└── uv.lock                 # Cryptographically locked dependency tree
```

## 🚀 Key Features

- **Scalable Web Agent Architecture:** Optimized for handling heavy web automation workloads concurrently.
- **Automated Newsletter Service:** Intelligent workflow engine found in `newsletter_service.py` to aggregate, summarize, and deliver web insights.
- **Dynamic Prompt Engineering:** Isolated prompt configurations (`prompts.py`) to easily tweak AI instructions without altering application runtime logic.
- **Strict Type Validation:** Native type safety using `custom_types.py` to minimize runtime exceptions during data parsing.
- **Modern Packaging Ecosystem:** Powered by `uv` for ultra-fast, reproducible local builds and execution.

## 🛠️ Getting Started

### Prerequisites

Ensure you have the `uv` toolchain installed on your machine. If you don't have it, run:

```bash
# macOS/Linux
curl -LsSf https://astral.sh | sh

# Windows
powershell -c "irm https://astral.sh | iex"
```

### 1. Installation

Clone the repository, change into the workspace, and synchronize your locked dependencies:

```bash
cd scalable-web-ai-agent
uv sync
```
*This command reads the `uv.lock` file and automatically configures a isolated local virtual environment (`.venv`).*

### 2. Environment Variables

Create a local `.env` file in the root directory to store your credentials (e.g., LLM provider API keys, scraping endpoints):

```bash
# Example .env configuration
OPENAI_API_KEY="your-api-key-here"
LOG_LEVEL="INFO"
```

### 3. Execution

Launch the AI agent using the unified runtime wrapper:

```bash
uv run run.py
```

## 🔧 Core Components Guide

### `newsletter_service.py`
Houses the execution pipeline of the agent. It manages asynchronous web traversal, data ingestion/scraping, and handles formatting layouts for automated delivery.

### `prompts.py`
Centralized repository for instructions given to the agent. System prompts, agent personas, and context retrieval variables are localized here for easy version control.

### `custom_types.py`
Enforces type constraints across your web data pipeline. Ensures that unvetted web-scraped data maps directly to your agent's internal data formats securely.

## 🧪 Development

### Dependency Management
To add a new library package safely to `pyproject.toml` and update your lockfile:

```bash
uv add <package-name>
```

### Code Quality & Formatting
Run your formatters or test suites inside the locked virtual environment context:

```bash
uv run ruff check .
```

# DeepAgents – Research Agent (Customized)

🚀 This repo is my hands-on customization of **DeepAgents**, a “deep” agent pattern built on **LangGraph + LangChain**.
Compared to a basic tool-calling agent, DeepAgents supports:
- ✅ Planning (todo-style)
- ✅ Sub-agents (delegation / context quarantine)
- ✅ A virtual file workspace (read/write files during the run)
- ✅ Strong system prompting for long, multi-step tasks

<img src="deep_agents.png" alt="deep agent" width="600"/>

---

## 🔍 What’s in this repo?

### 📂 Structure
- `src/` → the **deepagents library source code** (local package implementation)
- `examples/` → runnable demos, including the **Research Agent**
- `tests/` → unit tests for the library

---

## 🧠 Research Agent Demo (Two Options)

I included two ways to run the same “research deep agent” idea:

### ✅ Option A — Run the `.py` example using the **local source (`src/`)**
This uses the local `deepagents` implementation inside this repo.

- File: `examples/research/research_agent.py`
- Includes: **research subagent + critique subagent** (two-agent workflow)

**Typical flow:** search → draft report → critique → revise → finalize.

### ✅ Option B — Run the Notebook using the **public pip package**
This version is designed like a tutorial notebook and uses the installed `deepagents` package.

- Notebook: `examples/research/NotebookVersion/research_agent.ipynb`
- Includes: researcher workflow + clearer output inspection in notebook format
- Note: notebook version may differ slightly depending on the installed package version.

---

## ⚙️ Quickstart

### 1) Create a virtual environment
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
```
### 2) Install dependencies

### For local development (uses src/):

```bash
pip install -e .
```

### For the public library only (pip install):

```bash
pip install deepagents
```

### 3) Research demo dependencies

### The research agent uses Tavily search:

```bash
pip install tavily-python
```

Set your API key:
```bash
# Windows (cmd):
set TAVILY_API_KEY=YOUR_KEY
```

## ▶️ Run the Research Agent
### Run the .py version
```bash
python examples/research/research_agent.py
```

### Run the notebook
```bash
jupyter notebook
# then open:
# examples/research/NotebookVersion/research_agent.ipynb
```

## ✨ Why “Deep Agents” (vs normal tool agents)?

A normal agent often does: think → tool → answer.

DeepAgents is designed for longer tasks by adding:

1) Planning you can track

2) Subagents for delegation (and reducing context pollution)

3) A workspace (files) to build outputs like final_report.md

## 🙏 Credits / Attribution

This repo is based on the open-source DeepAgents project from the LangChain ecosystem.
My additions focus on documenting + experimenting with the research-agent workflow (Python + Notebook versions).

## 📌 Roadmap (Personal)

 Add a simple evaluation script (quality + consistency)

 Add guardrails (max iterations / max tool calls)

 Add more example agents (coding agent / data agent)


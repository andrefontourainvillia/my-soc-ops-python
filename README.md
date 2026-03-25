<div align="center">

# 🎯 Soc Ops

**Social Bingo for in-person mixers — powered by AI agent engineering**

*Find people who match the prompts. Get 5 in a row. Make connections that matter.*

[![Python](https://img.shields.io/badge/Python-3.13+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![HTMX](https://img.shields.io/badge/HTMX-hypermedia-blue?style=flat-square)](https://htmx.org/)
[![Jinja2](https://img.shields.io/badge/Jinja2-template-B41717?style=flat-square)](https://jinja.palletsprojects.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

</div>

---

## ✨ What is Soc Ops?

Soc Ops is a **live, browser-based Social Bingo** app built for in-person events. Players get a randomised 5×5 board of icebreaker prompts — find real people around the room who match each square, mark them off, and shout **BINGO** when you land 5 in a row.

But there's a twist: **this repo is also a hands-on GitHub Copilot workshop**. You'll use VS Code Agent Mode to redesign the UI, invent custom quiz themes, and ship new features — all guided by AI.

---

## 🚀 Key Features

| Feature | Details |
|---------|---------|
| 🎲 **Randomised boards** | Every player gets a unique 5×5 grid |
| 🆓 **Free space** | Centre square is always free — instant head start |
| ✅ **Live win detection** | Rows, columns, and diagonals are checked in real time |
| 🎉 **Bingo celebration** | Animated modal fires the moment you hit 5 in a row |
| 🔄 **Instant reset** | New game, new board — no page reload needed |
| 📱 **Responsive** | Looks great on phones, tablets, and laptops |

---

## 🛠️ Tech Stack

```
FastAPI  ·  Jinja2 templates  ·  HTMX (no JS framework)  ·  Custom CSS utilities
Python 3.13+  ·  uv package manager  ·  Pydantic models  ·  In-memory sessions
```

---

## ⚡ Quick Start

> **Prerequisites:** Python 3.13+, [uv](https://docs.astral.sh/uv/), Git

```bash
# 1. Clone the repo
git clone https://github.com/andrefontourainvillia/my-soc-ops-python.git soc-ops
cd soc-ops

# 2. Install dependencies
uv sync

# 3. Start the server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# 4. Open your browser → http://localhost:8000
```

> 💡 **DevContainer users:** Open in VS Code → *Reopen in Container* for a fully pre-configured environment.

---

## 🎓 Workshop Lab Guide

This repo doubles as an interactive Copilot workshop. Work through the parts in order to go from zero to AI-powered full-stack developer:

| Part | Title | Time | What You'll Do |
|------|-------|------|----------------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | 5 min | Review prerequisites and set expectations |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | 15 min | Clone, configure, and teach the AI about your codebase |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | 15 min | Redesign the UI with a creative theme of your choice |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | 10 min | Build a custom agent that generates themed bingo prompts |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | 20 min | Ship new features using TDD and design agents together |

> 📝 All lab guides are available offline in the [`workshop/`](workshop/) folder.

---

## 🏗️ Project Structure

```
app/
├── main.py          # Route handlers (thin layer)
├── models.py        # Immutable Pydantic models & GameState enum
├── game_logic.py    # Pure game mechanics (generate, toggle, check)
├── game_service.py  # Session-backed orchestration
├── data.py          # Bingo prompt pool
├── static/          # CSS utilities
└── templates/       # Jinja2 + HTMX partials
workshop/            # Offline lab guides
tests/               # Pytest suite
```

---

## 🤝 Contributing

This project follows the [Contributor Covenant](CODE_OF_CONDUCT.md). See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

<div align="center">

Made with ☕ and GitHub Copilot · [MIT License](LICENSE)

</div>

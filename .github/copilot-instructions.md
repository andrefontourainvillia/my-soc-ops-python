# Copilot Instructions for Soc Ops

## Mandatory Checklist
Run all three before finishing any change:
1. **Lint:** `uv run ruff check .`
2. **Build/Run:** `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`
3. **Test:** `uv run pytest`

Setup: `uv sync` · Port `8000` · Prefer VS Code tasks when available.

## Project Snapshot
FastAPI + Jinja2 + HTMX social bingo game · Python 3.13+ · in-memory sessions · custom CSS utilities.

## Architecture
- `app/models.py` — immutable Pydantic models, `GameState` enum.
- `app/game_logic.py` — pure mechanics (`generate_board`, `toggle_square`, `check_bingo`).
- `app/game_service.py` — session-backed `GameSession` orchestration.
- `app/main.py` — thin route handlers, middleware, template rendering.
- `app/data.py` — question pool constants.
- `app/templates/components/*` — HTMX partials (`start_screen`, `game_screen`, `bingo_board`, `bingo_modal`).

Game rules → `game_logic.py` · State flow → `game_service.py` · Routes stay thin in `main.py`.

## Conventions
- Small, typed functions; preserve immutability patterns in models/logic.
- Reuse HTMX patterns (`hx-post`, `hx-target`, `hx-swap`) and classes from `app/static/css/app.css`.
- Keep accessibility attributes already in templates.

## Pitfalls
- Sessions reset on restart (in-memory). Session secret is hardcoded — don't extend this.
- Browser Codespaces: set port 8000 to Public; see [workshop/01-setup.md](../workshop/01-setup.md).
- Never use VS Code Simple Browser.

## Start Here
`app/models.py` → `app/game_logic.py` → `app/game_service.py` → `app/main.py` → `app/static/css/app.css`

## Reference Links
- [CSS utilities](instructions/css-utilities.instructions.md) · [Frontend design](instructions/frontend-design.instructions.md) · [General rules](instructions/general.instructions.md) · [Workshop guide](../workshop/GUIDE.md)

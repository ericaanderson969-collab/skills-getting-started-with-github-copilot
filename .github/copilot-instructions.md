# Copilot Instructions

## Project Overview

- This repository is a learning exercise for GitHub Copilot.
- The backend is a FastAPI application in `src/app.py`.
- The browser UI is served from `src/static/` and talks to the backend's `/activities` endpoints.
- Activity data is stored in memory and resets whenever the server restarts.
- Exercise prompts and workflow steps under `.github/` are part of the learning experience; preserve them unless a task explicitly asks to change them.

## Development

- Install dependencies with `pip install -r requirements.txt`.
- Run the app from the repository root with `python -m uvicorn src.app:app --reload` (serves on `http://127.0.0.1:8000`).
- Run tests with `pytest`.
- Pytest adds the repository root to `sys.path` via `pytest.ini`.

## Change Guidelines

- Keep API changes consistent with the existing FastAPI routes and response shapes.
- When changing activity signup behavior, account for unknown activities and duplicate signups; keep the in-memory `activities` structure consistent with the frontend's expectations.
- Keep frontend changes in `src/static/` and use the existing fetch-based API integration unless the task calls for a broader change.
- Add or update focused tests in `tests/` for backend behavior. The existing test suite is minimal, so do not treat its current coverage as comprehensive.
- Avoid adding dependencies unless the task requires them.
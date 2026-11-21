# AgentArena — HTML, CSS & JavaScript MVP

A responsive, browser-based prototype for the AgentArena AI-agent reliability benchmarking concept.

## Run it
1. Extract the ZIP file.
2. Open `index.html` in Chrome, Edge or Firefox.
3. Go to **New benchmark**, select a task, repetition count, prompt condition and fault scenario.
4. Click **Run benchmark**.
5. Review the dashboard, history, traces and report. Export results as CSV.

No installation or build process is required.

## Included features
- Overview dashboard with experiment, success, recovery and timing metrics.
- Benchmark configuration for three sample tasks.
- Two clearly labelled scripted agent profiles (Agent A and Agent B).
- Repeated executions (k = 3, 5 or 10).
- Standard and meaning-preserving prompt-variation demo condition.
- Mock normal API, timeout, HTTP 429 and connection-drop scenarios.
- Side-by-side agent results, observable execution traces and report.
- Browser-local experiment history using `localStorage`.
- CSV export.

## Important implementation boundary
This is a **frontend-only simulation**. The two agent profiles are deterministic JavaScript simulations, not autonomous AI agents. Faults are simulated in the browser; no real API requests are intercepted. Metrics such as token usage and actual provider cost are not claimed. The UI is designed as a hackathon prototype and integration point.

## Suggested next backend integration
The supplied project brief proposes React/Vite, FastAPI, Python agent execution, mock API middleware and SQLite. This plain HTML/CSS/JS version intentionally keeps the frontend dependency-free. A production/hackathon backend can expose endpoints such as:
- `POST /api/experiments` — create an experiment
- `POST /api/experiments/{id}/run` — execute the benchmark
- `GET /api/experiments/{id}` — fetch metrics and traces
- `GET /api/experiments` — experiment history

Keep task data, fault schedules, budgets and expected outcomes identical for agents being compared. Use rule-based ground-truth checks for objective tasks.

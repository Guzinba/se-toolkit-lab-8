# Observability Skill

## Purpose
Help users investigate errors using logs and traces.

## Tools
- `logs_search(query, limit)` — search VictoriaLogs by LogsQL
- `logs_error_count(service, minutes)` — count errors for a service
- `traces_list(service, limit)` — list recent traces
- `traces_get(trace_id)` — fetch full trace by ID

## Flow
1. User asks about errors → use `logs_error_count`
2. If errors found → `logs_search` for details
3. If trace_id in logs → `traces_get` for full trace
4. Summarize concisely, no raw JSON dumps

## Examples
- "Any errors in backend LMS last 10 minutes?" → check logs_error_count("backend", 10)
- "Show trace abc123" → traces_get("abc123")

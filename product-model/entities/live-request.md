---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Logs.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_usage.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/operations.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/livetrace_handler.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/proxylog.go"
    }
  ],
  "domain": "live-requests"
}
---




# Live request

The in-memory subject observed and interrupted while a request is executing.

## Information kept

- **Request** — the request identity associating attempts, usage and live activity.
- **Model** — the requested outward model being executed.
- **Endpoint** — the operation family used by the request.
- **Token label** — the non-secret Token name/hint associated with a request.
- **Start time** — the instant the request began.
- **Progress** — the current in-memory request progress.
- **Status** — the current in-memory execution status and observed progress of the active request.
- **Interruption** — the cancellation outcome for the live operation.

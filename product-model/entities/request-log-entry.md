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
  ]
}
---




# Request log entry

A recorded request attempt/outcome presented through staff and Account-scoped projections.

## Information kept

- **Request** — the request identity associating attempts, usage and live activity.
- **Attempt** — the forwarding attempt associated with the request.
- **Time** — the instant this request attempt was recorded.
- **Token label** — the non-secret Token name/hint associated with a request.
- **Model** — the requested outward model name retained for this attempt.
- **Endpoint** — the operation family used by the request.
- **Status** — the observed HTTP status for this recorded request attempt.
- **Latency** — the observed request/attempt duration.
- **Tokens** — recognized input/output/total usage and applicable interrupted-text estimation.
- **Error category** — the classified validation, admission or upstream failure information.
- **Routing details** — the selected route/member/group and attempt information.
- **Upstream details** — the safe retained upstream outcome metadata; untrusted error strings have no universal secrecy guarantee.

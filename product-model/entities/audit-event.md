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
  "domain": "audit"
}
---




# Audit event

An operator-visible record of who performed an audited action and its result.

## Information kept

- **Actor** — the actual acting principal, including staff acting on a member target.
- **Action** — the action recorded by the relevant audit hook.
- **Subject** — the affected Product subject.
- **Time** — the instant the administrative action was recorded.
- **Outcome** — the successful, failed or skipped observed result.
- **Status** — the HTTP/result status associated with the audited administrative action.
- **Category** — the classified recorded event or failure category.

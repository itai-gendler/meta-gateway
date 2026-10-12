---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "apply-audit-retention"
    },
    {
      "type": "entity",
      "id": "audit-event"
    }
  ],
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



# Audit retention removes only the records selected by its configured age and row limits

Configured age/row cleanup and removed count; no request-log-retention parity

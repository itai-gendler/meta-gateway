---
{
  "entities": [
    {
      "entity": "audit-event",
      "shows": [
        "Actor",
        "Action",
        "Subject",
        "Time",
        "Outcome",
        "Status",
        "Category"
      ]
    },
    {
      "entity": "runtime-settings",
      "collects": [
        "Editable values"
      ]
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



# Audit

Recorded operator actions, their actual Actors and outcomes, with retention cleanup input.

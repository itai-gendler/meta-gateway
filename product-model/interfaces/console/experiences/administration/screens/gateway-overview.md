---
{
  "entities": [
    {
      "entity": "usage-record",
      "shows": [
        "Time",
        "Model",
        "Tokens",
        "Recorded cost",
        "Status"
      ]
    },
    {
      "entity": "request-log-entry",
      "shows": [
        "Status",
        "Latency"
      ]
    },
    {
      "entity": "connection",
      "shows": [
        "Status"
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



# Gateway overview

The gateway operational overview presents recognized usage, recorded configured cost and request/connection outcomes.

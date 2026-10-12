---
{
  "entities": [
    {
      "entity": "request-log-entry",
      "shows": [
        "Request",
        "Attempt",
        "Time",
        "Token label",
        "Model",
        "Endpoint",
        "Status",
        "Latency",
        "Tokens",
        "Error category",
        "Routing details",
        "Upstream details"
      ]
    },
    {
      "entity": "usage-record",
      "shows": [
        "Recorded cost"
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



# Request logs

Recorded request attempts and joined configured costs, including staff-only routing and upstream details.

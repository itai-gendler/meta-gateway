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
        "Error category"
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



# Own request logs

The current Account request projection groups attempts and shows common facts with recorded cost.

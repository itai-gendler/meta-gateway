---
{
  "kind": "primary",
  "routes": {
    "main": "A requests listed"
  },
  "steps": [
    {
      "text": "Read requests for the selected time and filters.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-request-logs"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the attempt record. Consult the usage ledger entry.",
      "kind": "condition",
      "entities": [
        {
          "entity": "request-log-entry",
          "effect": "reads",
          "facts": [
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
          "effect": "reads",
          "facts": [
            "Recorded cost"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::own-request-logs"
        }
      },
      "actor": "member"
    },
    {
      "text": "Requests show actual recorded cost joined by request identity; personal results exclude routing/upstream details.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-request-logs"
        }
      },
      "actor": "member"
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








# Browse request logs requests listed

## Trigger

Read requests for the selected time and filters.

## Outcome

Requests show actual recorded cost joined by request identity; personal results exclude routing/upstream details.

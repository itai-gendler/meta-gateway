---
{
  "kind": "primary",
  "routes": {
    "main": "D requests listed"
  },
  "steps": [
    {
      "text": "Read requests for the selected time and filters.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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
            "Error category",
            "Routing details",
            "Upstream details"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Requests show actual recorded cost joined by request identity; personal results exclude routing/upstream details.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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

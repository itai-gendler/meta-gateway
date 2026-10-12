---
{
  "kind": "primary",
  "routes": {
    "main": "D requests observed"
  },
  "steps": [
    {
      "text": "Subscribe to current live activity.",
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
      "text": "Consult the Live request.",
      "kind": "condition",
      "entities": [
        {
          "entity": "live-request",
          "effect": "reads",
          "facts": [
            "Request",
            "Model",
            "Endpoint",
            "Token label",
            "Start time",
            "Progress",
            "Status",
            "Interruption"
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
      "text": "Current request identity, progress and status are presented until the stream ends.",
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








# Watch live requests requests observed

## Trigger

Subscribe to current live activity.

## Outcome

Current request identity, progress and status are presented until the stream ends.

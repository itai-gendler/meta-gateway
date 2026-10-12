---
{
  "kind": "edge",
  "routes": {
    "main": "R stream disconnected"
  },
  "steps": [
    {
      "text": "Subscribe to current live activity.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::live-requests"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The live observation stream disconnects.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::live-requests"
        }
      }
    },
    {
      "text": "Observation ends; no durable live-request history or lossless reconnection is promised.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::live-requests"
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








# Watch live requests stream disconnected

## Trigger

The live observation stream disconnects.

## Outcome

Observation ends; no durable live-request history or lossless reconnection is promised.

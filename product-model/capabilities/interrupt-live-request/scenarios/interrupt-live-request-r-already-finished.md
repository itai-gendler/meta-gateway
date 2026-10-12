---
{
  "kind": "edge",
  "routes": {
    "main": "R already finished"
  },
  "steps": [
    {
      "text": "Select the active operation to interrupt.",
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
      "text": "The request has already completed before interruption is attempted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::live-requests"
        }
      }
    },
    {
      "text": "The finished-request outcome is returned and no stale operation is cancelled.",
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








# Interrupt request already finished

## Trigger

The request has already completed before interruption is attempted.

## Outcome

The finished-request outcome is returned and no stale operation is cancelled.

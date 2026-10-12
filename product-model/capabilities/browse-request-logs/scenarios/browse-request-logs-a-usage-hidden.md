---
{
  "kind": "validation",
  "routes": {
    "main": "A usage hidden"
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
      "text": "team user request visibility is disabled.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-request-logs"
        }
      }
    },
    {
      "text": "The local profile request-list boundary returns its visibility refusal; this does not imply all own usage-summary endpoints are blocked.",
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








# Browse request logs usage hidden

## Trigger

Member request visibility is disabled.

## Outcome

The Account request-list boundary returns its visibility refusal; this does not imply all own usage-summary endpoints are blocked.

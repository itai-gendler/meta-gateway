---
{
  "kind": "primary",
  "routes": {
    "main": "R old events removed"
  },
  "steps": [
    {
      "text": "Supply or use the configured audit retention choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::audit"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Remove the audit record.",
      "kind": "product",
      "entities": [
        {
          "entity": "audit-event",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::audit"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Expired/excess audit entries are removed and the removal count is returned.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::audit"
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








# Apply audit retention old events removed

## Trigger

Supply or use the configured audit retention choice.

## Outcome

Expired/excess audit entries are removed and the removal count is returned.

---
{
  "kind": "primary",
  "routes": {
    "main": "A overview shown"
  },
  "steps": [
    {
      "text": "Open the current overview.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::personal-overview"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the usage ledger entry. Consult the attempt record.",
      "kind": "condition",
      "entities": [
        {
          "entity": "usage-record",
          "effect": "reads",
          "facts": [
            "Time",
            "Model",
            "Tokens",
            "Recorded cost",
            "Status"
          ]
        },
        {
          "entity": "request-log-entry",
          "effect": "reads",
          "facts": [
            "Status",
            "Latency"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::personal-overview"
        }
      },
      "actor": "member"
    },
    {
      "text": "Recognized usage, recorded cost and applicable local profile/Token/forwarding destination summaries are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::personal-overview"
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








# Read overview overview shown

## Trigger

Open the current overview.

## Outcome

Recognized usage, recorded cost and applicable Account/Token/connection summaries are presented.

---
{
  "kind": "primary",
  "routes": {
    "main": "R overview shown"
  },
  "steps": [
    {
      "text": "Open the current overview.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::gateway-overview"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the usage ledger entry. Consult the attempt record. Consult the Connection.",
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
        },
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::gateway-overview"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Recognized usage, recorded cost and applicable local profile/Token/forwarding destination summaries are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::gateway-overview"
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








# Read overview overview shown

## Trigger

Open the current overview.

## Outcome

Recognized usage, recorded cost and applicable Account/Token/connection summaries are presented.

---
{
  "kind": "primary",
  "routes": {
    "main": "D events listed"
  },
  "steps": [
    {
      "text": "Read the audit inventory.",
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
      "text": "Consult the audit record.",
      "kind": "condition",
      "entities": [
        {
          "entity": "audit-event",
          "effect": "reads",
          "facts": [
            "Actor",
            "Action",
            "Subject",
            "Time",
            "Outcome",
            "Status",
            "Category"
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
      "text": "Actual Actor, action, subject, time and outcome are presented.",
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








# Browse audit events events listed

## Trigger

Read the audit inventory.

## Outcome

Actual Actor, action, subject, time and outcome are presented.

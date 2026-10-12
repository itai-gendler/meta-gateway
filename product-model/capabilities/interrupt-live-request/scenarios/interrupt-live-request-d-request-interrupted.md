---
{
  "kind": "primary",
  "routes": {
    "main": "D request interrupted"
  },
  "steps": [
    {
      "text": "Select the active operation to interrupt.",
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
            "Status"
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
      "text": "Save changes to the Live request.",
      "kind": "product",
      "entities": [
        {
          "entity": "live-request",
          "effect": "changes",
          "facts": [
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
      "text": "Cancellation is requested and interruption information retained; finished requests cannot be interrupted.",
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








# Interrupt request request interrupted

## Trigger

Select the live request to interrupt.

## Outcome

Cancellation is requested and interruption information retained; finished requests cannot be interrupted.

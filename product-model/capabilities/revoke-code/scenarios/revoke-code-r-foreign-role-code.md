---
{
  "kind": "edge",
  "routes": {
    "main": "R foreign role code"
  },
  "steps": [
    {
      "text": "Select the code to revoke.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "A limited staff principal selects a code whose staff management audience is limited staff principal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      }
    },
    {
      "text": "The code operation refuses that audience without revoking the selected code.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      },
      "actor": "administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/CodePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go"
    }
  ]
}
---








# Revoke code foreign role code

## Trigger

An Administrator selects a code whose staff management audience is Administrator.

## Outcome

The code operation refuses that audience without revoking the selected code.

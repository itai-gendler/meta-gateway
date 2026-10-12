---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid credit"
  },
  "steps": [
    {
      "text": "Supply code kind, assignment/grant, label, validity, use limit and batch count.",
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
      "text": "The credit batch, face values, validity or use limit fail the supported bounds.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      }
    },
    {
      "text": "Credit issuance is rejected without creating the invalid codes.",
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








# Create code invalid credit

## Trigger

The credit batch, face values, validity or use limit fail the supported bounds.

## Outcome

Credit issuance is rejected without creating the invalid codes.

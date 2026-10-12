---
{
  "kind": "edge",
  "routes": {
    "main": "R policy placeholder missing"
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
      "text": "No valid policy exists for the required credit-code persistence placeholder.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      }
    },
    {
      "text": "Credit issuance fails without making credit redemption policy-scoped.",
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








# Create code policy placeholder missing

## Trigger

No valid policy exists for the required credit-code persistence placeholder.

## Outcome

Credit issuance fails without making credit redemption policy-scoped.

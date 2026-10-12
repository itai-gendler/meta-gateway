---
{
  "kind": "validation",
  "routes": {
    "main": "R admin role refused"
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
      "text": "A limited staff principal submits invitation/credit issuance for the limited staff principal management audience.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::codes"
        }
      }
    },
    {
      "text": "Issuance is refused and no limited staff principal-facing bearer code is returned.",
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








# Create code admin role refused

## Trigger

An Administrator submits invitation/credit issuance for the Administrator management audience.

## Outcome

Issuance is refused and no Administrator-facing bearer code is returned.

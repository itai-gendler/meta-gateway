---
{
  "kind": "primary",
  "routes": {
    "main": "D credit issued"
  },
  "steps": [
    {
      "text": "Supply code kind, assignment/grant, label, validity, use limit and batch count.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Establish the Credit code.",
      "kind": "product",
      "entities": [
        {
          "entity": "credit-code",
          "effect": "creates",
          "facts": [
            "Code credential",
            "Label",
            "Staff management audience",
            "Token grant",
            "Money grant",
            "Validity",
            "Use limit",
            "Uses",
            "Redemptions",
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "credit authoritys retain face values and staff management audience, return plaintext once, and use a persistence policy placeholder without policy-scoped redemption.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Create code credit issued

## Trigger

Supply code kind, assignment/grant, label, validity, use limit and batch count.

## Outcome

Credit codes retain face values and staff management audience, return plaintext once, and use a persistence policy placeholder without policy-scoped redemption.

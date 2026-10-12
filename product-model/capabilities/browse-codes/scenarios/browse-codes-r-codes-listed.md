---
{
  "kind": "primary",
  "routes": {
    "main": "R codes listed"
  },
  "steps": [
    {
      "text": "Read the relevant inventory.",
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
      "text": "Consult the Invitation code. Consult the Credit code.",
      "kind": "condition",
      "entities": [
        {
          "entity": "invitation-code",
          "effect": "reads",
          "facts": [
            "Label",
            "Assigned role",
            "Policy",
            "Initial tokens",
            "Initial money",
            "Validity",
            "Use limit",
            "Uses",
            "Revocation"
          ]
        },
        {
          "entity": "credit-code",
          "effect": "reads",
          "facts": [
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
          "place": "console::administration::codes"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Staff-visible invitation and credit authority metadata is presented, without recoverable stored plaintext.",
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








# Browse codes codes listed

## Trigger

Read the relevant inventory.

## Outcome

Staff-visible invitation and credit code metadata is presented, without recoverable stored plaintext.

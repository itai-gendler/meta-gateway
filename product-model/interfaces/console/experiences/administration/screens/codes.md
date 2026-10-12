---
{
  "entities": [
    {
      "entity": "invitation-code",
      "shows": [
        "Label",
        "Assigned role",
        "Policy",
        "Initial tokens",
        "Initial money",
        "Validity",
        "Use limit",
        "Uses",
        "Revocation"
      ],
      "collects": [
        "Label",
        "Assigned role",
        "Policy",
        "Initial tokens",
        "Initial money",
        "Validity",
        "Use limit"
      ]
    },
    {
      "entity": "credit-code",
      "shows": [
        "Label",
        "Staff management audience",
        "Token grant",
        "Money grant",
        "Validity",
        "Use limit",
        "Uses",
        "Redemptions",
        "Revocation"
      ],
      "collects": [
        "Label",
        "Staff management audience",
        "Token grant",
        "Money grant",
        "Validity",
        "Use limit"
      ]
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



# Codes

The invitation/credit subject shows assignments, staff management audience, validity and consumed uses.

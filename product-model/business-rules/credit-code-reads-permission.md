---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "credit-code",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        }
      ],
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
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "actors": [
        "administrator"
      ],
      "when": [
        {
          "fact": "Staff management audience",
          "is": "Member"
        }
      ]
    },
    {
      "configuredBy": "credit-code"
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



# Deployment administrator, Owner or Administrator or execution under Credit code may read Credit code

Deployment administrator and Owner manage Credit codes. Administrator management is limited to the Member staff-management audience. Redemption uses the actual presented usable code, its face values, remaining global uses and the per-Account uniqueness check; staff-management audience does not assign a redemption role.

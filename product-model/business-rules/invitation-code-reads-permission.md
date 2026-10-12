---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invitation-code",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::entry"
        }
      ],
      "facts": [
        "Code credential",
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
          "fact": "Assigned role",
          "is": "Member"
        }
      ]
    },
    {
      "configuredBy": "invitation-code"
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



# Deployment administrator, Owner or Administrator or execution under Invitation code may read Invitation code

Deployment administrator and Owner manage invitations for supported assignments. Administrator management is limited to Member assignments. The actual presented, usable invitation permits its assigned registration and consumption; another invitation of the same type conveys no authority.

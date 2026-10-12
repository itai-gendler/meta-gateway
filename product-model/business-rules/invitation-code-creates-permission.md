---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invitation-code",
      "effect": "creates",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
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



# Deployment administrator, Owner or Administrator may create Invitation code

Deployment administrator and Owner manage invitations for supported assignments. Administrator management is limited to Member assignments. The actual presented, usable invitation permits its assigned registration and consumption; another invitation of the same type conveys no authority.

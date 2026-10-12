---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member",
      "effect": "creates",
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
        "Account association"
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
      ]
    },
    {
      "configuredBy": "invitation-code"
    },
    {
      "configuredBy": "oauth-settings",
      "when": [
        {
          "entity": "oauth-settings",
          "fact": "Registration",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---




# Deployment administrator, Owner or Administrator or execution under Invitation code or execution under OAuth settings may create Member Account association

Establishing or dropping Account association changes the fixed Product role held, not the human. The presented invitation must assign this exact role and remain valid; configured OAuth registration establishes Member, never Administrator. Staff scope and protected Owner association remain independent guards.

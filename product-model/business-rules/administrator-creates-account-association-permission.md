---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "administrator",
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
      "configuredBy": "invitation-code"
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



# Deployment administrator, Owner or execution under Invitation code may create Administrator Account association

Establishing or dropping Account association changes the fixed Product role held, not the human. The presented invitation must assign this exact role and remain valid; configured OAuth registration establishes Member, never Administrator. Staff scope and protected Owner association remain independent guards.

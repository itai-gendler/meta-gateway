---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "owner",
      "effect": "removes",
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
  "permits": [],
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



# No Actor may remove Owner through ordinary Account removal

Establishing or dropping Account association changes the fixed Product role held, not the human. Owner establishment occurs only when no Owner association exists, under first-owner mode establishment; ordinary role reassignment does not create a replacement Owner.

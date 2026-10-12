---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "recovery-link",
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
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
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



# Deployment administrator, Owner may remove Recovery link

Deployment administrator and Owner issue and clean up Account-bound recovery authority. Only the actual presented, usable recovery authority enables replacement of its subject's password and consumption of that authority.

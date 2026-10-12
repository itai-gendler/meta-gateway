---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "recovery-link",
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
        "Account",
        "Validity",
        "Consumption",
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
      "configuredBy": "recovery-link"
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



# Deployment administrator, Owner or execution under Recovery link may read Recovery link

Deployment administrator and Owner issue and clean up Account-bound recovery authority. Only the actual presented, usable recovery authority enables replacement of its subject's password and consumption of that authority.

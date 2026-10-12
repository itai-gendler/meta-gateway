---
{
  "entities": [
    {
      "entity": "access-policy",
      "shows": [
        "Name",
        "All models",
        "Models",
        "Route members",
        "Token limit",
        "Request rate",
        "Personal routing",
        "Request preference editing"
      ],
      "collects": [
        "Name",
        "All models",
        "Models",
        "Route members",
        "Token limit",
        "Request rate",
        "Personal routing",
        "Request preference editing"
      ]
    },
    {
      "entity": "route",
      "shows": [
        "Model name/pattern"
      ]
    },
    {
      "entity": "route-member",
      "shows": [
        "Route",
        "Connection",
        "Status"
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



# Access and routing

The access-policy subject presents explicit model/member grants and personal-configuration permissions.

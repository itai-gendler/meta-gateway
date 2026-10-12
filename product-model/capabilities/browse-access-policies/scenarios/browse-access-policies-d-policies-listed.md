---
{
  "kind": "primary",
  "routes": {
    "main": "D policies listed"
  },
  "steps": [
    {
      "text": "Read the relevant inventory.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Access policy.",
      "kind": "condition",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "reads",
          "facts": [
            "Name",
            "All models",
            "Models",
            "Route members",
            "Token limit",
            "Request rate",
            "Personal routing",
            "Request preference editing"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Defined access policies and their grants are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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








# Browse access policies policies listed

## Trigger

Read the relevant inventory.

## Outcome

Defined access policies and their grants are presented.

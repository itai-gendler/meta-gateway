---
{
  "kind": "primary",
  "routes": {
    "main": "D policy created"
  },
  "steps": [
    {
      "text": "Supply the policy definition.",
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
      "text": "Establish the Access policy.",
      "kind": "product",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "creates",
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
      "text": "The policy exists with its normalized grants and limits.",
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








# Create access policy policy created

## Trigger

Supply the policy definition.

## Outcome

The policy exists with its normalized grants and limits.

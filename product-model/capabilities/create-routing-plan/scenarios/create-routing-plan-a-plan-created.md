---
{
  "kind": "primary",
  "routes": {
    "main": "A plan created"
  },
  "steps": [
    {
      "text": "Supply a non-empty plan name.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "Establish the Routing plan.",
      "kind": "product",
      "entities": [
        {
          "entity": "routing-plan",
          "effect": "creates",
          "facts": [
            "Name",
            "Account",
            "Default selection",
            "Model arrangements",
            "Token selections"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "A new owned named plan exists with its initial arrangements.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/MemberModelsPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/member/RouteOrderDialog.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/team_access.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/team.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go#savePlan"
    }
  ]
}
---









# Create routing plan plan created

## Trigger

Supply a non-empty plan name.

## Outcome

A new owned named plan exists with its initial arrangements.

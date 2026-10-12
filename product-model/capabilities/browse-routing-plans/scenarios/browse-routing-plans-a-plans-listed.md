---
{
  "kind": "primary",
  "routes": {
    "main": "A plans listed"
  },
  "steps": [
    {
      "text": "Read personal personal arrangements.",
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
      "text": "Consult the Routing plan.",
      "kind": "condition",
      "entities": [
        {
          "entity": "routing-plan",
          "effect": "reads",
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
      "text": "Owned named and implicit-default plans are returned.",
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
    }
  ]
}
---








# Browse routing plans plans listed

## Trigger

Read personal routing plans.

## Outcome

Owned named and implicit-default plans are returned.

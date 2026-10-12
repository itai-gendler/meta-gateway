---
{
  "kind": "validation",
  "routes": {
    "main": "A routing disabled"
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
      "text": "The current policy or team user-routing visibility disables personal routing management.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      }
    },
    {
      "text": "The plan/order operation returns routing-not-allowed and retains saved arrangements.",
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








# Browse routing plans routing disabled

## Trigger

The current policy or member-routing visibility disables personal routing management.

## Outcome

The plan/order operation returns routing-not-allowed and retains saved arrangements.

---
{
  "kind": "edge",
  "routes": {
    "main": "A plan limit"
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
      "text": "Twenty retained plans already exist for this login identity, including its implicit default if present.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      }
    },
    {
      "text": "Named-plan creation is refused; an existing implicit default counts toward the insertion limit.",
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










# Create routing plan plan limit

## Trigger

Twenty retained plans already exist for this Account, including its implicit default if present.

## Outcome

Named-plan creation is refused; an existing implicit default counts toward the insertion limit.

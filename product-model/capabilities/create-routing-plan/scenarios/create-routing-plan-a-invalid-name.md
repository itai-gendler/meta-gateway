---
{
  "kind": "validation",
  "routes": {
    "main": "A invalid name"
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
      "text": "The supplied model, group or plan name fails its supported non-empty/length requirements.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      }
    },
    {
      "text": "The named resource operation is rejected without saving the invalid name.",
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









# Create routing plan invalid name

## Trigger

The supplied model, group or plan name fails its supported non-empty/length requirements.

## Outcome

The named resource operation is rejected without saving the invalid name.

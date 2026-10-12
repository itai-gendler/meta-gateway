---
{
  "kind": "primary",
  "routes": {
    "main": "A site order restored"
  },
  "steps": [
    {
      "text": "Select the model arrangement reset.",
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
      "text": "Save changes to the Routing plan.",
      "kind": "product",
      "entities": [
        {
          "entity": "routing-plan",
          "effect": "changes",
          "facts": [
            "Model arrangements"
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
      "text": "That model returns to current upstream destination ordering; the plan and other model arrangements remain.",
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








# Reset upstream order site order restored

## Trigger

Select the model arrangement reset.

## Outcome

That model returns to current site ordering; the plan and other model arrangements remain.

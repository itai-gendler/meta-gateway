---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "routing-plan",
      "effect": "changes",
      "contexts": [
        {
          "place": "console::personal"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "member"
        }
      ],
      "when": [
        {
          "entity": "access-policy",
          "fact": "Personal routing",
          "is": true
        },
        {
          "entity": "team-settings",
          "fact": "Routing visibility",
          "is": true
        }
      ]
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



# The related Member may change Routing plan

A related Member manages its owned routing plans when its current Policy permits personal routing and Team settings expose routing management. Inference consults the actual selected or implicit-default owned plan only while the fresh Policy still permits personal routing, independently of management visibility. Full-administration Account cleanup removes the Account's plans.

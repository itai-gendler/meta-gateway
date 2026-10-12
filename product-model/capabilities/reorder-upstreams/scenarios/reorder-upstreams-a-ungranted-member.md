---
{
  "kind": "validation",
  "routes": {
    "main": "A ungranted member"
  },
  "steps": [
    {
      "text": "Supply the ordered granted-upstream choices for a model.",
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
      "text": "The arrangement contains a duplicate, wrong-model, ungranted or invalidly weighted upstream binding.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      }
    },
    {
      "text": "Saving is refused; no unauthorized arrangement is retained.",
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








# Reorder upstreams ungranted member

## Trigger

The arrangement contains a duplicate, wrong-model, ungranted or invalidly weighted member.

## Outcome

Saving is refused; no unauthorized arrangement is retained.

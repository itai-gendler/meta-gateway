---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "reorder-upstreams"
    },
    {
      "type": "capability",
      "id": "reset-upstream-order"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "entity",
      "id": "routing-plan"
    },
    {
      "type": "entity",
      "id": "route-member"
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



# Personal arrangements contain only correct-model granted unique bindings

Saving permits only unique currently granted members of the correct model, with weights from 1 through 1000, at most 500 model arrangements and 200 entries per arrangement. Current disabled entries do not enter the custom pool. A custom model pool omits members absent from its list; untouched models retain site selection. Reset removes the model entry and returns current site order. Current policy, connection and health filters still apply.

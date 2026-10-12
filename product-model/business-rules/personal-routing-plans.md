---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-routing-plans"
    },
    {
      "type": "capability",
      "id": "create-routing-plan"
    },
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




# Plan management visibility does not erase existing inference selection

Named-plan creation is refused when the Account already retains twenty plans, including its implicit default if present. The implicit default is created on first arrangement write without that count guard: twenty named plans created first can therefore coexist with a subsequently created default. Personal management requires both policy routing permission and routing visibility. Inference resolves the selected owned plan or implicit default independently of visibility. Revoked policy routing permission fails Token authentication whenever such a plan exists, even when its arrangements are empty. Resetting one model removes only that arrangement and retains the plan.

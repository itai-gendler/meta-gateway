---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "explain-route"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
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
      "target": "internal/routing/scoring.go#pick"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go#pickWeighted"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/models.go#NormalizeRoutingMode"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/routing.go#evaluate"
    }
  ]
}
---

# Weighted mode picks in proportion to member weights only

Under Weighted, observed latency and failures never affect the pick, whatever the deployment's settings. A member with zero weight never wins. If every member has zero weight, the pick is uniform.

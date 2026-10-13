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
      "target": "internal/routing/scoring.go#scoreFor"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/runtimeconfig/runtimeconfig.go"
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

# Auto mode scores members by the deployment's own latency and error settings

Under Auto, latency scoring applies when the effective runtime settings enable latency-aware routing, and error scoring applies when they enable error-aware routing. With neither enabled, the pick is weight-proportional, as under Weighted.

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
      "target": "internal/routing/scoring.go#adaptiveScore"
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

# Adaptive mode always scores members by observed latency and failures

Under Adaptive, latency scoring and error scoring both apply, whatever the deployment's settings.

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
      "target": "internal/routing/routing.go#SelectSticky"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go#pickWeighted"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go#adaptiveScore"
    }
  ]
}
---


# Selection uses the highest eligible priority tier

Ordinary selection chooses among the highest-priority eligible members, by the policy the Route's Routing mode selects. Disabled, unavailable-credential, previously attempted and otherwise disqualified candidates remain excluded. Eligible affinity can retain its bound channel across priority changes. If only cooldown disqualifies candidates, the last resort chooses highest priority, then earliest cooldown expiry, then the earliest retained member identity. Where latency or error scoring applies, a member's base weight has a floor of one; latency scoring multiplies it by 3000/(3000+latency in milliseconds), and error scoring multiplies it by max(1-propensity, 0.05) for observed failure propensity. Every pick applies the concurrency adjustment, which keeps a 0.01 floor when saturated. Explanation omits transient concurrency adjustment.

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




# Selection uses the highest eligible priority tier with mode-specific weights

Ordinary selection chooses among the highest-priority eligible members. Weighted mode uses positive member weights; an all-zero pool falls back to a uniform choice. Auto follows effective global latency/error settings. Latency mode enables latency scoring; Adaptive enables latency and error scoring. Adaptive base weight has a floor of one; observed latency reduces it by 3000/(3000+latency in milliseconds), and observed failure propensity multiplies it by max(1-propensity, 0.05). The concurrency adjustment retains a 0.01 floor when saturated. Explanation omits transient concurrency adjustment. Eligible affinity can retain its bound channel across priority changes. If only cooldown disqualifies candidates, the last resort chooses highest priority, then earliest cooldown expiry, then the earliest retained member identity. Disabled, unavailable-credential, previously attempted and otherwise disqualified candidates remain excluded.

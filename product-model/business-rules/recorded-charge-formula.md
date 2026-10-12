---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "call-completions"
    },
    {
      "type": "capability",
      "id": "call-responses"
    },
    {
      "type": "capability",
      "id": "call-messages"
    },
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "edit-image"
    },
    {
      "type": "capability",
      "id": "vary-image"
    },
    {
      "type": "capability",
      "id": "create-embedding"
    },
    {
      "type": "entity",
      "id": "usage-record"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/relay.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_health.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_keypool.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/usage.go"
    }
  ]
}
---



# Recognized usage is charged by the selected layer and multiplicative adjustments

Recorded configured cost is ((prompt + cache-creation tokens)/1000 × prompt price + completion/1000 × completion price + cache-read/1000 × cache price + per-request price) × model billing multiplier × first matching time multiplier. Cache price at or below zero falls back to the selected layer's prompt price. Tiers are selected by prompt plus cache-creation tokens, excluding cache reads; excess uses the last configured tier, not a promise that it is numerically most expensive. Missing window matches use one. Invalid/non-finite cost becomes zero.

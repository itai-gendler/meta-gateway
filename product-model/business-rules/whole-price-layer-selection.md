---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-route-member"
    },
    {
      "type": "capability",
      "id": "edit-model-metadata"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "entity",
      "id": "route-member"
    },
    {
      "type": "entity",
      "id": "model-metadata"
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



# The first priced whole layer supplies every selected unit price

A priced route-member layer wins as a whole; otherwise exposed-name metadata is considered, followed by actual forwarded-name metadata when the exposed name is unpriced. Prompt, completion or per-request price above zero, or configured tiers, establishes a layer; cache-only price does not. A zero field in the selected layer remains zero rather than falling through. Tiers override flat prices. Invalid tier/window data is discarded with the implemented flat-price fallback.

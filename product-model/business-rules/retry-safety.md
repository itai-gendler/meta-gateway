---
{
  "appliesTo": [
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
      "id": "probe-image-generation"
    },
    {
      "type": "capability",
      "id": "probe-image-edit"
    },
    {
      "type": "capability",
      "id": "call-responses"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "entity",
      "id": "connection"
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



# Unsafe writes and exposed partial streams are never blindly replayed

Image writes do not replay; Responses replay follows implemented safety conditions; exposed partial streams prevent replay

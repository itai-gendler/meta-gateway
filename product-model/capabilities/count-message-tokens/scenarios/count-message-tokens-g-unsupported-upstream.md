---
{
  "kind": "edge",
  "routes": {
    "main": "G unsupported upstream"
  },
  "steps": [
    {
      "text": "Submit the model and message input with the downstream credential.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client"
    },
    {
      "text": "The selected upstream does not support the requested token-count contract.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      }
    },
    {
      "text": "The unsupported upstream result is distinguished; endpoint parity is not invented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client"
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








# Count message tokens unsupported upstream

## Trigger

The selected upstream does not support the requested token-count contract.

## Outcome

The unsupported upstream result is distinguished; endpoint parity is not invented.

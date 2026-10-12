---
{
  "kind": "validation",
  "routes": {
    "main": "G routing permission revoked"
  },
  "steps": [
    {
      "text": "Submit a model and local text history request with the downstream credential.",
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
      "text": "A selected or implicit-default personal plan exists while the linked policy has revoked personal routing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      }
    },
    {
      "text": "Token authentication fails even if that retained plan has no custom arrangement.",
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








# Call chat completions routing permission revoked

## Trigger

A selected or implicit-default personal plan exists while the linked policy has revoked personal routing.

## Outcome

Token authentication fails even if that retained plan has no custom arrangement.

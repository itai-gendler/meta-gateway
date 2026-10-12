---
{
  "kind": "edge",
  "routes": {
    "main": "G interrupted estimate"
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
      "text": "A qualifying 2xx text stream is interrupted after output bytes, without valid usage.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      }
    },
    {
      "text": "The recognized fallback estimates completion as floor(bytes/4), prompt zero; images do not use this estimation.",
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








# Call chat completions interrupted estimate

## Trigger

A qualifying 2xx text stream is interrupted after output bytes, without valid usage.

## Outcome

The recognized fallback estimates completion as floor(bytes/4), prompt zero; images do not use this estimation.

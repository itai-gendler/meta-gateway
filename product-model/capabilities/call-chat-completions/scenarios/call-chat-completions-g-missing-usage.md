---
{
  "kind": "edge",
  "routes": {
    "main": "G missing usage"
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
      "text": "The response supplies no recognized positive token total.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      }
    },
    {
      "text": "No usage/counter booking occurs, including any per-request charge; the response outcome is still returned.",
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








# Call chat completions missing usage

## Trigger

The response supplies no recognized positive token total.

## Outcome

No usage/counter booking occurs, including any per-request charge; the response outcome is still returned.

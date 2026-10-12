---
{
  "kind": "edge",
  "routes": {
    "main": "G image failure no replay"
  },
  "steps": [
    {
      "text": "Supply the image variation input and downstream credential.",
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
      "text": "The upstream image write fails or returns no usable image output.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      }
    },
    {
      "text": "The failure/current outcome is returned without replay; no successful browser saved image result is saved.",
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








# Vary image image failure no replay

## Trigger

The upstream image write fails or returns no usable image output.

## Outcome

The failure/current outcome is returned without replay; no successful browser Image run is saved.

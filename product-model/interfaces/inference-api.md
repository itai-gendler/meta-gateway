---
{
  "type": "api",
  "actors": [
    "gateway-client"
  ],
  "languages": [
    "en"
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
  ],
  "entryPoints": [
    {
      "api": "/v1"
    }
  ]
}
---



# Inference api

The downstream contract for model discovery, the supported inference operations and authenticated Token credit reporting.

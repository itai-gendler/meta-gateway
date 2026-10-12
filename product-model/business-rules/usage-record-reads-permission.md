---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "usage-record",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        }
      ],
      "facts": [
        "Request",
        "Time",
        "Account attribution",
        "Token attribution",
        "Model",
        "Endpoint",
        "Tokens",
        "Cache tokens",
        "Recorded cost",
        "Status"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "member"
        }
      ]
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



# Deployment administrator, Owner or the related Member may read Usage record

Deployment administrator and Owner read administrative usage. A related Member reads usage attributed to its own Account. Usage visibility affects the inspected detailed surface and does not deny every aggregate or budget display.

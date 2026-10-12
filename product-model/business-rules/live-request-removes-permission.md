---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "live-request",
      "effect": "removes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        },
        {
          "place": "inference-api"
        }
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
      "configuredBy": "system-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "member"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Logs.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_usage.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/operations.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/livetrace_handler.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/proxylog.go"
    }
  ]
}
---



# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token or Member using Account token may remove Live request

Mapped request execution creates, advances and finishes its in-memory live operation under the actual configured request authority. Deployment administrator and Owner observe and interrupt active operations. Product completion and expiry remove live tracking; no durable live-history retention is implied.

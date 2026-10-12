---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "live-request",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Request",
        "Model",
        "Endpoint",
        "Token label",
        "Start time",
        "Progress",
        "Status",
        "Interruption"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
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



# Deployment administrator, Owner may read Live request

Mapped request execution creates, advances and finishes its in-memory live operation under the actual configured request authority. Deployment administrator and Owner observe and interrupt active operations. Product completion and expiry remove live tracking; no durable live-history retention is implied.

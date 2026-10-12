---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid mapping"
  },
  "steps": [
    {
      "text": "Supply replacement forwarding destination settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The submitted endpoint, request/response or payload mapping fails save-time validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "The forwarding destination settings are rejected and its valid stored configuration remains.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Channels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ChannelModels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_connections.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_credentials.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/discovery.go"
    }
  ]
}
---








# Edit connection invalid mapping

## Trigger

The submitted endpoint, request/response or payload mapping fails save-time validation.

## Outcome

The connection settings are rejected and its valid stored configuration remains.

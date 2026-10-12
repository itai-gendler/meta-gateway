---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid target"
  },
  "steps": [
    {
      "text": "Supply a concrete observed model and diagnostic input.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The concrete model or selected forwarding destination test target is invalid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      }
    },
    {
      "text": "The direct test is refused before an upstream inference call.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
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








# Test connection model invalid target

## Trigger

The concrete model or selected connection test target is invalid.

## Outcome

The direct test is refused before an upstream inference call.

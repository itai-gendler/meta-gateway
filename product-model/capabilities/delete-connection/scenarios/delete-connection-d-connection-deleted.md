---
{
  "kind": "primary",
  "routes": {
    "main": "D connection deleted"
  },
  "steps": [
    {
      "text": "Select the forwarding destination to remove.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Remove the Connection. Remove the Route member.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "removes",
          "from": "Enabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Enabled",
          "with": "connection"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The forwarding destination and dependent outward-model routing bindings are removed.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Delete connection connection deleted

## Trigger

Select the connection to remove.

## Outcome

The connection and dependent route-member bindings are removed.

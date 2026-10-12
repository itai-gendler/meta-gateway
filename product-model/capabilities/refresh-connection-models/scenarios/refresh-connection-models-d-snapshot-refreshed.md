---
{
  "kind": "primary",
  "routes": {
    "main": "D snapshot refreshed"
  },
  "steps": [
    {
      "text": "Refresh the forwarding destination model snapshot.",
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
      "text": "Consult the Connection.",
      "kind": "condition",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Model sync mode",
            "Credential association"
          ]
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
      "text": "Save changes to the Connection. Establish the Discovered model. Remove the Discovered model.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Model snapshot"
          ]
        },
        {
          "entity": "discovered-model",
          "effect": "creates",
          "facts": [
            "Name",
            "Connection",
            "Credential evidence",
            "Observed at"
          ],
          "as": "new-observation"
        },
        {
          "entity": "discovered-model",
          "effect": "removes",
          "as": "previous-observation"
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
      "text": "Manual refresh replaces candidate observations without adopting new routing; existing bindings are not generally deleted when a name disappears.",
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








# Refresh connection models snapshot refreshed

## Trigger

Refresh the connection model snapshot.

## Outcome

Manual refresh replaces candidate observations without adopting new routing; existing bindings are not generally deleted when a name disappears.

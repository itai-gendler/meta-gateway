---
{
  "kind": "primary",
  "routes": {
    "main": "D model test result"
  },
  "steps": [
    {
      "text": "Supply a concrete observed model and diagnostic input.",
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
      "text": "Consult the Connection. Consult the Discovered model.",
      "kind": "condition",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Base address",
            "Protocol",
            "Credential association"
          ]
        },
        {
          "entity": "discovered-model",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The direct model-test response is returned with diagnostic accounting behavior.",
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








# Test connection model model test result

## Trigger

Supply a concrete observed model and diagnostic input.

## Outcome

The direct model-test response is returned with diagnostic accounting behavior.

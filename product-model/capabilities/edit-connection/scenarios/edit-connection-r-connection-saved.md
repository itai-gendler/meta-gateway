---
{
  "kind": "primary",
  "routes": {
    "main": "R connection saved"
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
      "text": "Save changes to the Connection.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Name",
            "Site",
            "Credential association",
            "Base address",
            "Protocol",
            "Priority",
            "Weight",
            "Model sync mode",
            "Routing controls",
            "Forwarding settings",
            "Group name"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The selected forwarding destination settings are saved, including its model-sync mode and validated mappings.",
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








# Edit connection connection saved

## Trigger

Supply replacement connection settings.

## Outcome

The selected connection settings are saved, including its model-sync mode and validated mappings.

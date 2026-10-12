---
{
  "kind": "edge",
  "routes": {
    "main": "R remote auth failure"
  },
  "steps": [
    {
      "text": "Request a remote user credential check.",
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
      "text": "The supported remote user credential adapter receives remote authentication failure.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "Retain the Connection credential-check failure category and check time.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Connectivity observations"
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
      "text": "The observed upstream credential-operation failure/category is returned without inventing balance or usable keys.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go#Probe"
    }
  ]
}
---










# Check upstream account remote auth failure

## Trigger

The supported upstream Account adapter receives remote authentication failure.

## Outcome

The observed Account-operation failure/category is returned without inventing balance or usable keys.

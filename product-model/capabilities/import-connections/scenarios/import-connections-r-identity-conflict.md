---
{
  "kind": "edge",
  "routes": {
    "main": "R identity conflict"
  },
  "steps": [
    {
      "text": "Supply import material and any required unlock input.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Imported destination/credential identity conflicts with retained configuration.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      }
    },
    {
      "text": "The import reports conflict for affected items without silently overwriting incompatible identity.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Exchange.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/SetupWizard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/exchange.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/exchange/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/webdav.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/webdavsync/service.go"
    }
  ]
}
---








# Import connections identity conflict

## Trigger

Imported destination/credential identity conflicts with retained configuration.

## Outcome

The import reports conflict for affected items without silently overwriting incompatible identity.

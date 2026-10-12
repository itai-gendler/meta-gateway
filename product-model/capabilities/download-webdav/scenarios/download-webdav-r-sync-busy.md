---
{
  "kind": "edge",
  "routes": {
    "main": "R sync busy"
  },
  "steps": [
    {
      "text": "Request or schedule a download.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A test, upload or download already holds the shared synchronization slot.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      }
    },
    {
      "text": "The busy outcome is returned without starting another concurrent remote operation.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
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








# Download webdav sync busy

## Trigger

A test, upload or download already holds the shared synchronization slot.

## Outcome

The busy outcome is returned without starting another concurrent remote operation.

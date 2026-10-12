---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid address"
  },
  "steps": [
    {
      "text": "Supply direction settings and protected credentials.",
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
      "text": "The supplied forwarding destination or remote address fails its address validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      }
    },
    {
      "text": "The settings are rejected before the requested saved destination replaces valid configuration.",
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








# Change webdav settings invalid address

## Trigger

The supplied connection or remote address fails its address validation.

## Outcome

The settings are rejected before the requested saved destination replaces valid configuration.

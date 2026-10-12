---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid document"
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
      "text": "The supplied import material fails supported parsing or strict decoding.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      }
    },
    {
      "text": "The document is rejected with its distinguished import category; no item from the invalid document is applied.",
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








# Import connections invalid document

## Trigger

The supplied import material fails supported parsing or strict decoding.

## Outcome

The document is rejected with its distinguished import category; no item from the invalid document is applied.

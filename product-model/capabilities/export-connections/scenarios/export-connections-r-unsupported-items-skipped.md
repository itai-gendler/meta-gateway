---
{
  "kind": "edge",
  "routes": {
    "main": "R unsupported items skipped"
  },
  "steps": [
    {
      "text": "Supply export format, explicit forwarding destinations when including secrets, and secret-inclusion choice.",
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
      "text": "Selected export contains credential/forwarding destination kinds the chosen representation cannot include.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      }
    },
    {
      "text": "Supported items are exported and skipped reasons are returned; universal round-trip parity is not promised.",
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








# Export connections unsupported items skipped

## Trigger

Selected export contains credential/connection kinds the chosen representation cannot include.

## Outcome

Supported items are exported and skipped reasons are returned; universal round-trip parity is not promised.

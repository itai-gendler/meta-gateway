---
{
  "kind": "validation",
  "routes": {
    "main": "R secret export refused"
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
      "text": "The direct export request asks for secrets while the Product's secret-export allowance is disabled.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      }
    },
    {
      "text": "Direct secret export is refused; WebDAV's service export is a separately selected operation.",
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








# Export connections secret export refused

## Trigger

The direct export request asks for secrets while the Product's secret-export allowance is disabled.

## Outcome

Direct secret export is refused; WebDAV's service export is a separately selected operation.

---
{
  "kind": "edge",
  "routes": {
    "main": "R partial import"
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
      "text": "Supported input contains both valid and individually skipped/invalid entries.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      }
    },
    {
      "text": "Establish the Site. Establish the Upstream API key in Enabled state. Establish the Connection in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "site",
          "effect": "creates",
          "facts": [
            "Name",
            "Base address",
            "Platform",
            "Status",
            "Call policy"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "creates",
          "facts": [
            "Site",
            "Credential",
            "Secret availability",
            "Status",
            "Model restrictions",
            "Priority",
            "Discovery evidence",
            "Remote token reference"
          ],
          "to": "Enabled",
          "with": "site"
        },
        {
          "entity": "connection",
          "effect": "creates",
          "facts": [
            "Name",
            "Site",
            "Credential association",
            "Base address",
            "Protocol",
            "Status",
            "Priority",
            "Weight",
            "Model snapshot",
            "Model sync mode",
            "Routing controls",
            "Forwarding settings",
            "Connectivity observations",
            "Group name"
          ],
          "to": "Enabled",
          "with": "site"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::exchange"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Valid items are applied and per-item skipped/error information is returned; whole-document atomicity is not promised.",
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








# Import connections partial import

## Trigger

Supported input contains both valid and individually skipped/invalid entries.

## Outcome

Valid items are applied and per-item skipped/error information is returned; whole-document atomicity is not promised.

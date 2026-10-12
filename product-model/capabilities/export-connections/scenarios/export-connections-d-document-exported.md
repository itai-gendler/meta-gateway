---
{
  "kind": "primary",
  "routes": {
    "main": "D document exported"
  },
  "steps": [
    {
      "text": "Supply export format, explicit forwarding destinations when including secrets, and secret-inclusion choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration::connection-export"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Site. Consult the Connection. Consult the Upstream API key. Consult the Upstream account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Name",
            "Base address",
            "Platform",
            "Status",
            "Call policy"
          ]
        },
        {
          "entity": "connection",
          "effect": "reads",
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
            "Connectivity observations"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "reads",
          "facts": [
            "Site",
            "Secret availability",
            "Status",
            "Model restrictions",
            "Priority",
            "Discovery evidence",
            "Remote token reference"
          ]
        },
        {
          "entity": "upstream-account",
          "effect": "reads",
          "facts": [
            "Site",
            "Credential availability",
            "Authentication mode",
            "Platform identity",
            "Status",
            "Account observations",
            "Check-in setting"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration::connection-export"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Supported selected items are exported with per-item skipped information; export is a projection of retained configuration.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration::connection-export"
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








# Export connections document exported

## Trigger

Supply export format, explicit connections when including secrets, and secret-inclusion choice.

## Outcome

Supported selected items are exported with per-item skipped information; export is a projection of retained configuration.

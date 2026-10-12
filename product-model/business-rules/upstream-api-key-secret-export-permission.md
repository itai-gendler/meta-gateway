---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "upstream-api-key",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration::exchange"
        },
        {
          "place": "management-api::administration::connection-export"
        }
      ],
      "facts": [
        "Credential"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ],
      "when": [
        {
          "entity": "operator-settings",
          "fact": "Secret export allowance",
          "is": true
        }
      ]
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



# Deployment administrator, Owner may read Upstream API key Credential

Deployment administrator or Owner administration; configured credential use by forwarding/discovery; no customer credential disclosure.

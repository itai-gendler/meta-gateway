---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "upstream-account",
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
        "Credential",
        "Cookie"
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



# Deployment administrator, Owner may read Upstream account Credential, Cookie

Deployment administrator or Owner administration; configured account/discovery/check-in execution.

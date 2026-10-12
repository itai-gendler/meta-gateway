---
{
  "entities": [
    {
      "entity": "site",
      "shows": [
        "Name",
        "Base address",
        "Platform",
        "Status",
        "Call policy"
      ],
      "collects": [
        "Name",
        "Base address",
        "Platform"
      ]
    },
    {
      "entity": "connection",
      "shows": [
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
      ],
      "collects": [
        "Name",
        "Site",
        "Credential association",
        "Base address",
        "Protocol",
        "Model sync mode"
      ]
    },
    {
      "entity": "upstream-api-key",
      "shows": [
        "Site",
        "Credential",
        "Secret availability",
        "Status",
        "Model restrictions",
        "Priority",
        "Discovery evidence",
        "Remote token reference"
      ],
      "collects": [
        "Credential"
      ]
    },
    {
      "entity": "upstream-account",
      "shows": [
        "Site",
        "Credential",
        "Cookie",
        "Credential availability",
        "Authentication mode",
        "Platform identity",
        "Status",
        "Account observations",
        "Check-in setting",
        "Model restrictions",
        "Priority"
      ],
      "collects": [
        "Credential",
        "Cookie",
        "Model restrictions",
        "Priority"
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




# Exchange

The file exchange process presents selected export/import projections and per-item results.

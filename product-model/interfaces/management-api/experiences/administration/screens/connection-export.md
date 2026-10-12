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
        "Credential association"
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
        "Check-in setting"
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



# Connection export

The selected export process presents the connection projection and specifically admitted credential disclosure.

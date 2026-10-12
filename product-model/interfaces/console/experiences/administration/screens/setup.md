---
{
  "entities": [
    {
      "entity": "runtime-settings",
      "shows": [
        "Effective values",
        "Sources"
      ],
      "collects": [
        "Editable values"
      ]
    },
    {
      "entity": "connection",
      "shows": [
        "Name",
        "Status",
        "Model snapshot"
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
      "entity": "system-token",
      "shows": [
        "Name",
        "Credential hint",
        "Credential"
      ],
      "collects": [
        "Name",
        "Model restrictions",
        "Scopes",
        "Token limit",
        "Money limit",
        "Expiry",
        "IP restrictions"
      ]
    },
    {
      "entity": "webdav-settings",
      "shows": [
        "Last result"
      ],
      "collects": [
        "Download connection",
        "Credential availability"
      ]
    },
    {
      "entity": "team-settings",
      "collects": [
        "Operating mode"
      ]
    },
    {
      "entity": "site",
      "collects": [
        "Name",
        "Base address",
        "Platform"
      ]
    },
    {
      "entity": "upstream-api-key",
      "collects": [
        "Credential"
      ]
    },
    {
      "entity": "upstream-account",
      "collects": [
        "Credential",
        "Cookie",
        "Authentication mode",
        "Platform identity"
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



# Setup

The first-access process retains configuration, connection/import progress and the issued credential until completion.

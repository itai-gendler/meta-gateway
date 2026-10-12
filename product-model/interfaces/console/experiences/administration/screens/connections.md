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
        "Status",
        "Priority",
        "Weight",
        "Model sync mode",
        "Routing controls",
        "Forwarding settings"
      ]
    },
    {
      "entity": "upstream-api-key",
      "shows": [
        "Site",
        "Secret availability",
        "Status",
        "Model restrictions",
        "Priority",
        "Discovery evidence",
        "Remote token reference"
      ],
      "collects": [
        "Site",
        "Credential",
        "Secret availability",
        "Status",
        "Model restrictions",
        "Priority"
      ]
    },
    {
      "entity": "upstream-account",
      "shows": [
        "Site",
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
        "Site",
        "Credential",
        "Cookie",
        "Credential availability",
        "Authentication mode",
        "Platform identity",
        "Status",
        "Check-in setting",
        "Model restrictions",
        "Priority"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Channels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ChannelModels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_connections.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_credentials.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/discovery.go"
    }
  ]
}
---




# Connections

The connection subject presents destinations, credential availability and observed upstream account/connectivity results.

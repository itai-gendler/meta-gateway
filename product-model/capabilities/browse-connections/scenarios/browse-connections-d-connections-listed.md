---
{
  "kind": "primary",
  "routes": {
    "main": "D connections listed"
  },
  "steps": [
    {
      "text": "Read the forwarding destination inventory.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "forwarding destination and safe credential metadata are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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








# Browse connections connections listed

## Trigger

Read the connection inventory.

## Outcome

Connection and safe credential metadata are presented.

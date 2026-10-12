---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "upstream-account",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        },
        {
          "place": "inference-api"
        }
      ],
      "facts": [
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
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "configuredBy": "system-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "unattended": true
    },
    {
      "configuredBy": "connection"
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




# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token or the scheduled Product or execution under Connection may read Upstream account

Deployment administrator and Owner manage upstream user credentials. Account synchronization, discovery, forwarding and native check-in consult the actual selected credential and its applicable enabled/authentication conditions. Scheduled native execution requires an enabled check-in setting, the relevant supported Site and credential, usable stored authority and a due enabled schedule. Its updates are account observations, not arbitrary stored-authority edits.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "upstream-account",
      "effect": "creates",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
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



# Deployment administrator, Owner may create Upstream account

Deployment administrator and Owner manage upstream user credentials. Account synchronization, discovery, forwarding and native check-in consult the actual selected credential and its applicable enabled/authentication conditions. Scheduled native execution requires an enabled check-in setting, the relevant supported Site and credential, usable stored authority and a due enabled schedule. Its updates are account observations, not arbitrary stored-authority edits.

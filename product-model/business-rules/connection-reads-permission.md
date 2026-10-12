---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connection",
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
        "Connectivity observations",
        "Group name"
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
      "configuredBy": "access-policy",
      "actors": [
        "member"
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



# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token or Member using Access policy or the scheduled Product or execution under Connection may read Connection

Deployment administrator and Owner manage Connections. Personal model/member projections use the current applicable Policy; forwarding uses the actual resolved Token, fresh Account/Policy constraints where linked, and selected connection. Scheduled discovery requires its configured enabled connection; scheduled WebDAV import follows its configured direction. These continuations do not grant arbitrary public Connection editing.

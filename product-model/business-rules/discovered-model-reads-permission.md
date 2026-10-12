---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "discovered-model",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Name",
        "Connection",
        "Credential evidence",
        "Observed at"
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



# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token or the scheduled Product or execution under Connection may read Discovered model

Full administrators refresh and read discovered candidates and adopt supported selections. Scheduled discovery refreshes candidates for the actual configured enabled connection. Manual mode retains a candidate snapshot; Auto mode also adopts routes and members. Unsaved preview persists no candidate.

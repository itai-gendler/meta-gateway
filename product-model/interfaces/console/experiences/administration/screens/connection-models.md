---
{
  "entities": [
    {
      "entity": "discovered-model",
      "shows": [
        "Name",
        "Connection",
        "Credential evidence",
        "Observed at"
      ]
    },
    {
      "entity": "route",
      "shows": [
        "Model name/pattern",
        "Status",
        "Forwarded-name mapping"
      ],
      "collects": [
        "Model name/pattern"
      ]
    },
    {
      "entity": "route-member",
      "shows": [
        "Connection",
        "Status",
        "Group name",
        "Forwarded-name mapping",
        "Health"
      ],
      "collects": [
        "Connection",
        "Status",
        "Group name",
        "Forwarded-name mapping"
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



# Connection models

The observed-model subject presents candidate names and configured bindings associated with this connection.

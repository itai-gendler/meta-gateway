---
{
  "kind": "primary",
  "routes": {
    "main": "D models listed"
  },
  "steps": [
    {
      "text": "Open the forwarding destination model subject.",
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
      "text": "Consult the Discovered model. Consult the Route. Consult the Route member.",
      "kind": "condition",
      "entities": [
        {
          "entity": "discovered-model",
          "effect": "reads",
          "facts": [
            "Name",
            "Connection",
            "Credential evidence",
            "Observed at"
          ]
        },
        {
          "entity": "route",
          "effect": "reads",
          "facts": [
            "Model name/pattern",
            "Status",
            "Forwarded-name mapping"
          ]
        },
        {
          "entity": "route-member",
          "effect": "reads",
          "facts": [
            "Connection",
            "Group name",
            "Status",
            "Forwarded-name mapping",
            "Health"
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
      "text": "Candidates, mapped names and binding state are shown independently of upstream callability.",
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








# Browse connection models models listed

## Trigger

Open the connection model subject.

## Outcome

Candidates, mapped names and binding state are shown independently of upstream callability.

---
{
  "kind": "primary",
  "routes": {
    "main": "R connection copied"
  },
  "steps": [
    {
      "text": "Select the forwarding destination to duplicate.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Connection.",
      "kind": "condition",
      "entities": [
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
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Establish the Connection in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "creates",
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
          ],
          "to": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A copied forwarding destination exists with the established duplication defaults.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
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








# Duplicate connection connection copied

## Trigger

Select the connection to duplicate.

## Outcome

A copied connection exists with the established duplication defaults.

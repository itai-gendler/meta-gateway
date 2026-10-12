---
{
  "kind": "edge",
  "routes": {
    "main": "R probe unavailable"
  },
  "steps": [
    {
      "text": "Supply destination, protocol, name and credential information.",
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
      "text": "The console saved a new forwarding destination, but its later verification is unavailable or fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "Establish the Site. Establish the Upstream API key in Enabled state. Establish the Connection in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "site",
          "effect": "creates",
          "facts": [
            "Name",
            "Base address",
            "Platform",
            "Status",
            "Call policy"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "creates",
          "facts": [
            "Site",
            "Credential",
            "Secret availability",
            "Status",
            "Model restrictions",
            "Priority",
            "Discovery evidence",
            "Remote token reference"
          ],
          "to": "Enabled",
          "with": "site"
        },
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
          "to": "Enabled",
          "with": "site"
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
      "text": "The saved forwarding destination remains and the later verification failure is shown; creation is not falsely reported rolled back.",
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









# Create connection probe unavailable

## Trigger

The console saved a new connection, but its later verification is unavailable or fails.

## Outcome

The saved connection remains and the later verification failure is shown; creation is not falsely reported rolled back.

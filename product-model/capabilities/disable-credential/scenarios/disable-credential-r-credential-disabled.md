---
{
  "kind": "primary",
  "routes": {
    "main": "R credential disabled"
  },
  "steps": [
    {
      "text": "Select the credential to disable.",
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
      "text": "For the selected API-credential kind, save changes to the Upstream API key in Disabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Disabled",
          "from": "Enabled"
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
      "text": "For the selected remote-user kind, save changes to the Upstream account in Disabled state.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Disabled",
          "from": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "The credential is disabled for ordinary selection or local profile operations.",
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









# Disable credential credential disabled

## Trigger

Select the credential to disable.

## Outcome

The credential is disabled for ordinary selection or Account operations.


## Decision points

### Selected credential kind

Which individually addressed credential kind was selected? Both branches finish with the selected credential operation result; they do not edit both credential instances.

- API key → apply the API-credential facts/status/removal branch.
- Upstream user → apply the user-credential facts/status/removal branch.

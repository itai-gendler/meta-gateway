---
{
  "kind": "primary",
  "routes": {
    "main": "D credential enabled"
  },
  "steps": [
    {
      "text": "Select the credential to enable.",
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
      "text": "For the selected API-credential kind, save changes to the Upstream API key in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Enabled",
          "from": "Disabled"
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
      "text": "For the selected remote-user kind, save changes to the Upstream account in Enabled state.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Enabled",
          "from": "Disabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      }
    },
    {
      "text": "The credential is enabled for applicable selection or local profile operations.",
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









# Enable credential credential enabled

## Trigger

Select the credential to enable.

## Outcome

The credential is enabled for applicable selection or Account operations.


## Decision points

### Selected credential kind

Which individually addressed credential kind was selected? Both branches finish with the selected credential operation result; they do not edit both credential instances.

- API key → apply the API-credential facts/status/removal branch.
- Upstream user → apply the user-credential facts/status/removal branch.

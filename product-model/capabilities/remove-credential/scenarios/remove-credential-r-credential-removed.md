---
{
  "kind": "primary",
  "routes": {
    "main": "R credential removed"
  },
  "steps": [
    {
      "text": "Select the credential to remove.",
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
      "text": "For the selected API-credential kind, remove the Upstream API key.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "removes",
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
      "text": "For the selected remote-user kind, remove the Upstream account.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "removes",
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
      "text": "The credential is removed from the managed pool.",
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









# Remove credential credential removed

## Trigger

Select the credential to remove.

## Outcome

The credential is removed from the managed pool.


## Decision points

### Selected credential kind

Which individually addressed credential kind was selected? Both branches finish with the selected credential operation result; they do not edit both credential instances.

- API key → apply the API-credential facts/status/removal branch.
- Upstream user → apply the user-credential facts/status/removal branch.

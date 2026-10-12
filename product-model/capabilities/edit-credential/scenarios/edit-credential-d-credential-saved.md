---
{
  "kind": "primary",
  "routes": {
    "main": "D credential saved"
  },
  "steps": [
    {
      "text": "Supply credential replacements and supported settings.",
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
      "text": "For the selected API-credential kind, save changes to the Upstream API key.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "changes",
          "facts": [
            "Credential",
            "Model restrictions",
            "Priority"
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
      "text": "For the selected remote-user kind, save changes to the Upstream account.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Credential",
            "Cookie",
            "Authentication mode",
            "Platform identity"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      }
    },
    {
      "text": "The credential settings are saved while blank replacement secrets preserve stored authority unless the corresponding explicit clear choice is supplied.",
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










# Edit credential credential saved

## Trigger

Supply credential replacements and supported settings.

## Outcome

The credential settings are saved while blank replacement secrets preserve stored authority unless the corresponding explicit clear choice is supplied.


## Decision points

### Selected credential kind

Which individually addressed credential kind was selected? Both branches finish with the selected credential operation result; they do not edit both credential instances.

- API key → apply the API-credential facts/status/removal branch.
- Upstream user → apply the user-credential facts/status/removal branch.

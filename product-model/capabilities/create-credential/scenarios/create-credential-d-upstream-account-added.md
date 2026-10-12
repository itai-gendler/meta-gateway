---
{
  "kind": "primary",
  "routes": {
    "main": "D upstream account added"
  },
  "steps": [
    {
      "text": "Supply the credential kind and its protected authority and metadata.",
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
      "text": "Create the Upstream account with supplied secret or cookie authority, authentication mode, platform identity, enabled status and retained selection defaults.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "creates",
          "to": "Enabled",
          "facts": [
            "Site",
            "Credential",
            "Cookie",
            "Credential availability",
            "Authentication mode",
            "Platform identity",
            "Status",
            "Account observations",
            "Check-in setting",
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
      "text": "The individually managed credential retains its supplied secret authority and saved enabled, model-restriction and priority choices; user credentials additionally retain their cookie, authentication kind and platform identity.",
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









# Create credential upstream account added

## Trigger

Supply the upstream user credential, secret or cookie, authentication mode and platform identity.

## Outcome

The Upstream account is retained at its Site with protected user authority and the supplied account-operation settings.

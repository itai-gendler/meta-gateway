---
{
  "kind": "primary",
  "routes": {
    "main": "D remote key created"
  },
  "steps": [
    {
      "text": "Supply the supported remote-key creation choice.",
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
      "text": "Consult the Upstream account. Consult the Site.",
      "kind": "condition",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "reads",
          "facts": [
            "Credential",
            "Cookie",
            "Authentication mode",
            "Platform identity",
            "Status"
          ]
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Platform",
            "Status"
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "When the remote user identity is missing and the self lookup succeeds, retain the observed Upstream account platform identity.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Platform identity"
          ]
        }
      ]
    },
    {
      "text": "When the returned secret is new, establish the enabled Upstream API key; otherwise reuse the matching local key.",
      "kind": "product",
      "entities": [
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
          "to": "Enabled"
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "Attach the resolved Upstream API key to the Connection when it differs from the current association.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "reads",
          "facts": [
            "Site",
            "Secret availability",
            "Remote token reference"
          ]
        },
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Credential association"
          ]
        }
      ]
    },
    {
      "text": "The upstream key creation result and usable key information are returned.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go#CreateKey"
    }
  ]
}
---













# Create upstream key remote key created

## Trigger

Supply the supported remote-key creation choice.

## Outcome

The upstream key creation result and usable key information are returned.

## Edge cases

- Resolve missing remote user identity when possible. Failure after remote creation or earlier local writes does not promise rollback.

## Decision points

### Local secret resolution

Is the created remote key's usable secret already retained locally?

- New usable secret → create an enabled local key and attach it.
- Matching retained secret → reuse that row and attach it.
- Masked response → reveal, then attempt bounded synchronization up to twice before classified failure if no usable key can be resolved.

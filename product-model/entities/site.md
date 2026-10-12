---
{
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
  ],
  "domain": "connections",
  "relations": [
    {
      "entity": "connection",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "upstream-api-key",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "upstream-account",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---



# Site

The upstream site whose platform and address inform connections and account operations.

## Information kept

- **Name** — the upstream Site's display name.
- **Base address** — the configured upstream service address.
- **Platform** — the upstream account platform kind, selecting supported account operations.
- **Status** — whether the upstream Site is enabled for applicable supported account and check-in operations.
- **Call policy** — the site-level routing and forwarding settings.

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
  "domain": "connection-models"
}
---



# Discovered model

An observed candidate name from a connection snapshot, distinct from an adopted route.

## Information kept

- **Name** — the Product-facing name identifying this instance.
- **Connection** — the connection providing the candidate or binding.
- **Credential evidence** — the credential discovery evidence that produced the candidate.
- **Observed at** — the time this discovery observation was made.

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
  "domain": "connections"
}
---




# Upstream account

An individually managed upstream user credential supporting account operations and native check-in.

## Information kept

- **Site** — the associated upstream site.
- **Credential** — the protected upstream user-token authority used by supported account operations or token-based relay.
- **Cookie** — protected upstream account cookie authority.
- **Credential availability** — whether applicable secret or cookie authority is present and usable.
- **Authentication mode** — the supported upstream account authentication kind.
- **Platform identity** — the remote account identifier required by its adapter.
- **Status** — the Enabled or Disabled credential choice checked by supported account operations and relay selection.
- **Account observations** — observed upstream balance, usage, account eligibility and operation results.
- **Check-in setting** — whether native check-in is enabled for this credential.

- **Model restrictions** — the retained per-credential model allowlist used where this credential supports relay.
- **Priority** — the retained per-credential preference tier used where this credential supports relay.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.

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




# Upstream API key

An individually managed upstream API credential with model evidence and selection settings.

## Information kept

- **Site** — the associated upstream site.
- **Credential** — the protected upstream API bearer secret used by its permitted relay/discovery contract.
- **Secret availability** — whether usable/decryptable secret material can be obtained for the operation.
- **Status** — the Enabled or Disabled credential choice used by the upstream pool.
- **Model restrictions** — the configured model-name allowlist or restrictions for this credential.
- **Priority** — the configured preference tier used by the relevant selector.
- **Discovery evidence** — the last model-discovery evidence associated with the credential.
- **Remote token reference** — the remote key identity and observed name/group where these have been observed or created.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.

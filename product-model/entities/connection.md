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
      "entity": "discovered-model",
      "verb": "offers",
      "cardinality": "one-to-many"
    },
    {
      "entity": "route-member",
      "verb": "provides",
      "cardinality": "one-to-many"
    }
  ]
}
---




# Connection

An upstream forwarding destination with a configured credential association and routing settings.

## Information kept

- **Group name** — the retained connection group used for grouping the configured upstream destinations.
- **Name** — the upstream forwarding destination's display name.
- **Site** — the associated upstream site.
- **Credential association** — the credential or credential pool configured for forwarding through the connection.
- **Base address** — the configured upstream service address.
- **Protocol** — the upstream protocol or provider adapter selected for the connection.
- **Status** — the Enabled or Disabled Connection choice used by applicable routing/discovery checks.
- **Priority** — the configured preference tier used by the relevant selector.
- **Weight** — the configured selection weight; zero is not a universal disabled state.
- **Model snapshot** — the last discovered model names and evidence, independently of adoption.
- **Model sync mode** — Manual candidate refresh or Auto adoption.
- **Routing controls** — connection-level selection, cooldown, affinity, blacklist and concurrency settings.
- **Forwarding settings** — configured endpoint, request/response/payload and protocol transformation settings.
- **Connectivity observations** — the observed ping or verification result, not a continuing uptime promise.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.

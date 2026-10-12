---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Models.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_routes.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/route.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/routing.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/unify.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_alias.go"
    }
  ],
  "domain": "models",
  "relations": [
    {
      "entity": "route-member",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---




# Route

The outward model name or pattern and its configured forwarding selection.

## Information kept

- **Model name/pattern** — the exposed concrete model name or wildcard matcher.
- **Status** — whether this outward model matcher is Enabled or Disabled.
- **Routing mode** — Auto, Weighted, Latency, Adaptive or Single-member selection; Auto follows the effective global selection settings.
- **Single member** — the optional pinned binding used while it is usable.
- **Forwarded-name mapping** — the configured outward-to-upstream model-name mapping.
- **Routing overrides** — the route-level forwarding and selection overrides.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.

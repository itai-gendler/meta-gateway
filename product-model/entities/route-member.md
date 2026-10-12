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
  "domain": "models"
}
---



# Route member

A binding from an outward route to a connection, carrying its group, mapping, price and health.

## Information kept

- **Route** — the route to which this binding belongs.
- **Connection** — the connection providing the candidate or binding.
- **Group name** — the member grouping value; route groups have no independent identity.
- **Status** — whether this individual routing binding is Enabled or Disabled.
- **Priority** — the configured preference tier used by the relevant selector.
- **Weight** — the configured selection weight; zero is not a universal disabled state.
- **Forwarded-name mapping** — the configured outward-to-upstream model-name mapping.
- **Price layer** — flat token/cache/request prices, optional tiers and time windows, selected as one whole layer.
- **Health** — the retained success/failure and selection health evidence.
- **Cooldown** — the temporary cooling deadline/evidence consulted by selection.
- **Manual intent** — whether this binding reflects deliberate operator selection.
- **Automatic origin** — whether discovery or another automatic operation established the binding.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.

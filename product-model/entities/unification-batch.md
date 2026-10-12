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



# Unification batch

Operator-visible history and snapshots for reversing a model-name unification.

## Information kept

- **Canonical name** — the unified model name chosen for the batch.
- **Changes** — the changes kept for visible reverse-replay history.
- **Original snapshots** — the whole original route/member information needed for identity-preserving reconstruction.
- **Created at** — the time the Product established this record.
- **Undo progress** — the applied and completed reverse operations, permitting partial or completed undo.

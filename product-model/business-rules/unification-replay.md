---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "unify-model-names"
    },
    {
      "type": "capability",
      "id": "undo-name-unification"
    },
    {
      "type": "capability",
      "id": "restore-original-route"
    },
    {
      "type": "entity",
      "id": "unification-batch"
    },
    {
      "type": "entity",
      "id": "route"
    },
    {
      "type": "entity",
      "id": "route-member"
    }
  ],
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
  ]
}
---



# Unification reverse replay preserves identities and protects later bindings

Whole-row snapshots, reverse replay, skipped completed operations, manual/other-batch protection, full-coverage deletion, identity-preserving reconstruction, name-conflict refusal

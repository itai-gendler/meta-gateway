---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "rename-route-group"
    },
    {
      "type": "capability",
      "id": "copy-route-group"
    },
    {
      "type": "capability",
      "id": "delete-route-group"
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



# Route-group operations change member values with their collision and copy guards

Rename/copy/delete affect member Group names/bindings; copy skips mapped/existing destination bindings and starts fresh health; default Route group has no Token-group default protection

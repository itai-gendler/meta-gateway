---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-route"
    },
    {
      "type": "capability",
      "id": "sync-model-catalog"
    },
    {
      "type": "entity",
      "id": "model-capability"
    },
    {
      "type": "entity",
      "id": "model-metadata"
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



# Concrete route bootstrap cannot fail or block its originating save

Concrete Route creation synchronously classifies locally and queues bounded/nonblocking external refresh; wildcard patterns skipped

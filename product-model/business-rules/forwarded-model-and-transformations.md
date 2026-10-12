---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-connection"
    },
    {
      "type": "capability",
      "id": "edit-route"
    },
    {
      "type": "capability",
      "id": "edit-route-member"
    },
    {
      "type": "capability",
      "id": "change-connection-model-alias"
    },
    {
      "type": "capability",
      "id": "remove-connection-model-alias"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "entity",
      "id": "route"
    },
    {
      "type": "entity",
      "id": "route-member"
    },
    {
      "type": "entity",
      "id": "connection"
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



# Configured mappings and alias moves preserve their actual precedence and binding facts

Member model mapping precedes Route mapping. Configured endpoint, protocol and request/response/payload transformations can change forwarded semantics. Alias moves preserve applicable member identity, groups, price, health and manual intent; an entire original route can move while preserving overrides where safe. Alias removal writes explicit identity mapping instead of clearing the mapping value, which still affects manual unchecking classification. Protected pin/conflicting bindings are refused.

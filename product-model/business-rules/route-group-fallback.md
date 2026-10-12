---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "explain-route"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
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



# Blank and unmatched named route groups use their implemented fallback pools

A blank requested group selects the full eligible pool. A named group selects its current matches; with none, default-group matches are tried; with none of those, selection falls back to the full pool.

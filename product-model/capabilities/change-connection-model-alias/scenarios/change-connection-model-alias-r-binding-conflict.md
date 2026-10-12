---
{
  "kind": "edge",
  "routes": {
    "main": "R binding conflict"
  },
  "steps": [
    {
      "text": "Supply the concrete source model and desired alias.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Alias movement would collide with existing or protected bindings.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      }
    },
    {
      "text": "The operation refuses the conflict without silently replacing the protected binding.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      },
      "actor": "owner"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_alias.go#SetChannelModelAlias"
    }
  ]
}
---









# Change connection model alias binding conflict

## Trigger

Alias movement would collide with existing or protected bindings.

## Outcome

The operation refuses the conflict without silently replacing the protected binding.

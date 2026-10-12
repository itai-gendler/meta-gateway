---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid concrete name"
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
      "text": "The source or alias is empty, wildcarded or otherwise not a valid concrete model name.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      }
    },
    {
      "text": "The alias operation is refused without moving bindings.",
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









# Change connection model alias invalid concrete name

## Trigger

The source or alias is empty, wildcarded or otherwise not a valid concrete model name.

## Outcome

The alias operation is refused without moving bindings.

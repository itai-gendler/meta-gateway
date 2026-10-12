---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid binding"
  },
  "steps": [
    {
      "text": "Supply the forwarding destination, group, forwarded name and initial binding settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The supplied model matcher/forwarding destination/group binding is invalid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      }
    },
    {
      "text": "The binding operation is refused without establishing the invalid association.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
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
    }
  ]
}
---








# Add route member invalid binding

## Trigger

The supplied route/connection/group binding is invalid.

## Outcome

The binding operation is refused without establishing the invalid association.

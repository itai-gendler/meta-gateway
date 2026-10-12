---
{
  "kind": "primary",
  "routes": {
    "main": "R member removed"
  },
  "steps": [
    {
      "text": "Select the binding or parked-binding cleanup.",
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
      "text": "Remove the Route member.",
      "kind": "product",
      "entities": [
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The selected bindings are removed.",
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








# Remove route member member removed

## Trigger

Select the binding or parked-member cleanup.

## Outcome

The selected bindings are removed.

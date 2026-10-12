---
{
  "kind": "primary",
  "routes": {
    "main": "H manual plain binding removed"
  },
  "steps": [
    {
      "text": "Select the binding to disable.",
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
      "text": "Remove the Route member. Remove the Route.",
      "kind": "product",
      "entities": [
        {
          "entity": "route-member",
          "effect": "removes",
          "with": "route",
          "from": "Enabled"
        },
        {
          "entity": "route",
          "effect": "removes",
          "from": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connection-models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Unchecking a plain manual binding removes it; the now-empty model matcher is cleaned when it has no remaining routing bindings.",
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
    }
  ]
}
---








# Disable route member manual plain binding removed

## Trigger

Select the binding to disable.

## Outcome

Unchecking a plain manual binding removes it; the now-empty route is cleaned when it has no remaining members.

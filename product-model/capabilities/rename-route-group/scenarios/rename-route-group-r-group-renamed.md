---
{
  "kind": "primary",
  "routes": {
    "main": "R group renamed"
  },
  "steps": [
    {
      "text": "Supply the existing and replacement group names.",
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
      "text": "Save changes to the Route member.",
      "kind": "product",
      "entities": [
        {
          "entity": "route-member",
          "effect": "changes",
          "facts": [
            "Group name"
          ]
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
      "text": "Applicable routing binding group names are changed.",
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








# Rename route group group renamed

## Trigger

Supply the existing and replacement group names.

## Outcome

Applicable member group names are changed.

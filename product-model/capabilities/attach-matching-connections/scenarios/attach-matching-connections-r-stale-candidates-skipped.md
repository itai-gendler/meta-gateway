---
{
  "kind": "edge",
  "routes": {
    "main": "R stale candidates skipped"
  },
  "steps": [
    {
      "text": "Preview exact or related matches, retain selections and submit.",
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
      "text": "Some previewed selections are disabled, unknown or no longer offer the matched model.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      }
    },
    {
      "text": "Establish the Route member in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "route-member",
          "effect": "creates",
          "facts": [
            "Route",
            "Connection",
            "Group name",
            "Status",
            "Priority",
            "Weight",
            "Forwarded-name mapping",
            "Price layer",
            "Health",
            "Cooldown",
            "Manual intent",
            "Automatic origin"
          ],
          "to": "Enabled"
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
      "text": "Current valid matches are added; stale entries contribute skipped outcomes; already-bound targets remain idempotent no-ops.",
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








# Attach matching connections stale candidates skipped

## Trigger

Some previewed selections are disabled, unknown or no longer offer the matched model.

## Outcome

Current valid matches are added; stale entries contribute skipped outcomes; already-bound targets remain idempotent no-ops.

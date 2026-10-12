---
{
  "kind": "primary",
  "routes": {
    "main": "D selection explained"
  },
  "steps": [
    {
      "text": "Supply the model and routing context to explain.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Route. Consult the Route member. Consult the Connection.",
      "kind": "condition",
      "entities": [
        {
          "entity": "route",
          "effect": "reads",
          "facts": [
            "Model name/pattern",
            "Status",
            "Routing mode",
            "Single member",
            "Forwarded-name mapping",
            "Routing overrides"
          ]
        },
        {
          "entity": "route-member",
          "effect": "reads",
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
          ]
        },
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Status",
            "Priority",
            "Weight",
            "Routing controls"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The current matching and candidate selection explanation is returned; it is not a reservation.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Explain route selection explained

## Trigger

Supply the model and routing context to explain.

## Outcome

The current matching and candidate selection explanation is returned; it is not a reservation.

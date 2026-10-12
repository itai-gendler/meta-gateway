---
{
  "kind": "primary",
  "routes": {
    "main": "H snapshot model adopted"
  },
  "steps": [
    {
      "text": "Supply the forwarding destination, group, forwarded name and initial binding settings.",
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
      "text": "Consult the Discovered model. Consult the Connection.",
      "kind": "condition",
      "entities": [
        {
          "entity": "discovered-model",
          "effect": "reads",
          "facts": [
            "Name",
            "Connection"
          ]
        },
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Model snapshot"
          ]
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
      "text": "Establish the Route in Enabled state. Establish the Route member in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "creates",
          "facts": [
            "Model name/pattern",
            "Status",
            "Routing mode",
            "Single member",
            "Forwarded-name mapping",
            "Routing overrides"
          ],
          "to": "Enabled"
        },
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
          "to": "Enabled",
          "with": "route"
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
      "text": "The forwarding destination-model selection establishes the concrete outward model matcher if needed and its selected binding.",
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








# Add route member snapshot model adopted

## Trigger

Supply the connection, group, forwarded name and initial binding settings.

## Outcome

The connection-model selection establishes the concrete outward route if needed and its selected binding.

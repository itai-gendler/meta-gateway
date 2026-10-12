---
{
  "kind": "primary",
  "routes": {
    "main": "S automatic adoption"
  },
  "steps": [
    {
      "text": "Refresh the forwarding destination model snapshot.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Connection.",
      "kind": "condition",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Model sync mode",
            "Credential association"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Connection. Establish the Discovered model. Remove the Discovered model. Establish the Route in Enabled state. Establish the Route member in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Model snapshot"
          ]
        },
        {
          "entity": "discovered-model",
          "effect": "creates",
          "facts": [
            "Name",
            "Connection",
            "Credential evidence",
            "Observed at"
          ],
          "as": "new-observation"
        },
        {
          "entity": "discovered-model",
          "effect": "removes",
          "as": "previous-observation"
        },
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
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Auto refresh retains observations and adopts newly observed candidate model bindings, preserving existing explicit enabled choices.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Channels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ChannelModels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_connections.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_credentials.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/discovery.go"
    }
  ]
}
---








# Refresh connection models automatic adoption

## Trigger

Refresh the connection model snapshot.

## Outcome

Auto refresh retains observations and adopts newly discovered route/member bindings, preserving existing explicit enabled choices.

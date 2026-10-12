---
{
  "kind": "primary",
  "routes": {
    "main": "R scheduled run"
  },
  "steps": [
    {
      "text": "The configured schedule is due.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "unattended": true
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
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "Save changes to the Connection. Establish the Discovered model. Remove the Discovered model.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "When the configured Connection uses Auto mode, establish the newly discovered Route and Route member; Manual refresh retains observations only.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Model sync mode",
            "Status"
          ]
        },
        {
          "entity": "route",
          "effect": "creates",
          "to": "Enabled",
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
          "effect": "creates",
          "to": "Enabled",
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
          "with": "route"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "The snapshot is refreshed; Auto can establish outward-model routing binding bindings and Manual retains candidates only.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
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








# Refresh connection models scheduled run

## Trigger

The configured schedule becomes due for refresh the configured credential's discovered model snapshot and adopt only under Auto mode.

## Outcome

The snapshot is refreshed; Auto can establish route/member bindings and Manual retains candidates only.

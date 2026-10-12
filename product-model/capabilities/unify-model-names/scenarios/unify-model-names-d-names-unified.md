---
{
  "kind": "primary",
  "routes": {
    "main": "D names unified"
  },
  "steps": [
    {
      "text": "Choose a canonical name and confirm the previewed risk.",
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
      "text": "Establish the Unification batch. Establish the Route in Enabled state. Establish the Route member in Enabled state. Remove the Route. Remove the Route member.",
      "kind": "product",
      "entities": [
        {
          "entity": "unification-batch",
          "effect": "creates",
          "facts": [
            "Canonical name",
            "Changes",
            "Original snapshots",
            "Created at",
            "Undo progress"
          ]
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
          "to": "Enabled",
          "as": "new-route"
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
          "as": "new-route-member",
          "with": "new-route"
        },
        {
          "entity": "route",
          "effect": "removes",
          "as": "old-route",
          "from": "Enabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "as": "old-route-member",
          "with": "old-route",
          "from": "Enabled"
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
      "text": "Applicable bindings are unified and a batch retains changes and original snapshots; superseded model matchers are removed only under full coverage.",
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








# Unify model names names unified

## Trigger

Choose a canonical name and confirm the previewed risk.

## Outcome

Applicable bindings are unified and a batch retains changes and original snapshots; superseded routes are removed only under full coverage.

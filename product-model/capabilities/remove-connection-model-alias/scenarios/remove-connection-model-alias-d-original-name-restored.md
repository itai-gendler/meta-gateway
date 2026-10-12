---
{
  "kind": "primary",
  "routes": {
    "main": "D original name restored"
  },
  "steps": [
    {
      "text": "Select the alias to remove.",
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "When every existing binding belongs to one source Route and no target exists, rename that Route in place. Move the existing Route member bindings to the chosen destination and retain identities, groups, prices, health and manual settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "changes",
          "facts": [
            "Model name/pattern"
          ],
          "as": "existing-source"
        },
        {
          "entity": "route-member",
          "effect": "changes",
          "facts": [
            "Route",
            "Forwarded-name mapping"
          ],
          "as": "existing-binding"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "When no target Route exists and in-place rename is unavailable, establish a Route using the source settings; with no prior bindings use an enabled default. A disabled source retains its disabled choice.",
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
          "to": "Enabled",
          "as": "enabled-target"
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
          "to": "Disabled",
          "as": "disabled-target"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "When no previous binding exists, establish an enabled Route member on the chosen target with its explicit forwarded-name mapping and automatic origin.",
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
          "to": "Enabled",
          "as": "new-binding"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "Remove only a superseded Route that is left without bindings after their move; keep a renamed route and every source that still has bindings.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "removes",
          "as": "emptied-source-enabled",
          "from": "Enabled"
        },
        {
          "entity": "route",
          "effect": "removes",
          "as": "emptied-source-disabled",
          "from": "Disabled"
        }
      ]
    },
    {
      "text": "Bindings are moved back where safe and an explicit identity mapping is saved.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_alias.go#SetChannelModelAlias"
    }
  ]
}
---












# Remove connection model alias original name restored

## Trigger

Select the alias to remove.

## Outcome

Bindings are moved back where safe and an explicit identity mapping is saved.

## Edge cases

- Only empty superseded sources are removed. Identity mapping also protects against a destination's historical route-level alias.

## Decision points

### Original-name destination

Does the original-name destination already exist, and how much of the alias source moves?

- Existing destination → reuse it and move the eligible bindings with explicit identity mapping.
- Absent destination, one whole source → rename that source in place and retain its identity and settings.
- Absent destination, partial source → clone the first source settings and enabled choice, clearing a pin that did not move, then move existing bindings.
- No prior binding → create an enabled destination if needed and an enabled automatic binding with identity mapping.

---
{
  "kind": "primary",
  "routes": {
    "main": "R original restored"
  },
  "steps": [
    {
      "text": "Select the original model matcher to restore.",
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
      "text": "Consult the Unification batch.",
      "kind": "condition",
      "entities": [
        {
          "entity": "unification-batch",
          "effect": "reads",
          "facts": [
            "Original snapshots",
            "Undo progress"
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
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner",
      "text": "When the snapshot retained Enabled for the Route, reconstruct that Route with its original identity and saved settings. Each reconstructed Route member independently retains its saved Enabled or Disabled choice; these are alternative binding outcomes.",
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
          "as": "restored-enabled"
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
          "as": "restored-enabled-enabled-binding",
          "with": "restored-enabled"
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
          "to": "Disabled",
          "as": "restored-enabled-disabled-binding",
          "with": "restored-enabled"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner",
      "text": "When the snapshot retained Disabled for the Route, reconstruct that Route with its original identity and saved settings. Each reconstructed Route member independently retains its saved Enabled or Disabled choice; these are alternative binding outcomes.",
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
          "to": "Disabled",
          "as": "restored-disabled"
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
          "as": "restored-disabled-enabled-binding",
          "with": "restored-disabled"
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
          "to": "Disabled",
          "as": "restored-disabled-disabled-binding",
          "with": "restored-disabled"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner",
      "text": "For a legacy archived original, change the retained Route back to its recorded previous enabled choice instead of reconstructing it.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "Disabled",
          "to": "Enabled",
          "as": "legacy-enabled-original"
        },
        {
          "entity": "route",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "Enabled",
          "to": "Disabled",
          "as": "legacy-disabled-original"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner",
      "text": "Retain the Unification batch undo progress on successful transaction commit; skip previously undone operations.",
      "kind": "product",
      "entities": [
        {
          "entity": "unification-batch",
          "effect": "changes",
          "facts": [
            "Undo progress"
          ]
        }
      ]
    },
    {
      "text": "The original model matcher and routing bindings return with their original identities and saved facts; its operation is marked undone.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/unify.go#RestoreDeletedRoute"
    }
  ]
}
---












# Restore original route original restored

## Trigger

Select the original route to restore.

## Outcome

The original route and members return with their original identities and saved facts; its operation is marked undone.


## Edge cases

- Each reconstructed matcher or binding keeps the Enabled or Disabled choice in its saved snapshot; restoration does not force it enabled.

- An existing same-name model blocks reconstruction. A legacy archived operation restores its previous enabled choice in place.

## Decision points

### Saved enabled choices

What enabled choices did the original snapshots retain?

- Enabled outward model → reconstruct the enabled model with its original identity; each binding keeps its own saved enabled choice.
- Disabled outward model → reconstruct the disabled model with its original identity; each binding keeps its own saved enabled choice.

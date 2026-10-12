---
{
  "kind": "primary",
  "routes": {
    "main": "D batch undone"
  },
  "steps": [
    {
      "text": "Select the unification history to undo.",
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
      "text": "Consult the Unification batch.",
      "kind": "condition",
      "entities": [
        {
          "entity": "unification-batch",
          "effect": "reads",
          "facts": [
            "Changes",
            "Original snapshots",
            "Undo progress"
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
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
          "place": "management-api::administration"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner",
      "text": "For a still-active route-created operation, remove the Route only after checking later manual and other active-batch bindings. Its Route member dependents are removed with it, retaining their actual enabled origins.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "removes",
          "from": "Enabled",
          "as": "batch-created-enabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Enabled",
          "as": "batch-created-enabled-enabled-binding",
          "with": "batch-created-enabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Disabled",
          "as": "batch-created-enabled-disabled-binding",
          "with": "batch-created-enabled"
        },
        {
          "entity": "route",
          "effect": "removes",
          "from": "Disabled",
          "as": "batch-created-disabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Enabled",
          "as": "batch-created-disabled-enabled-binding",
          "with": "batch-created-disabled"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Disabled",
          "as": "batch-created-disabled-disabled-binding",
          "with": "batch-created-disabled"
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
      "text": "For a recorded binding creation on a surviving destination, remove only that Route member; use its actual enabled or disabled origin.",
      "kind": "product",
      "entities": [
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Enabled",
          "as": "batch-created-enabled-binding"
        },
        {
          "entity": "route-member",
          "effect": "removes",
          "from": "Disabled",
          "as": "batch-created-disabled-binding"
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
      "text": "For a route-enabled or legacy archive operation, return the Route to its recorded previous enabled choice rather than reconstructing it.",
      "kind": "product",
      "entities": [
        {
          "entity": "route",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "Enabled",
          "to": "Disabled",
          "as": "previously-enabled-route"
        },
        {
          "entity": "route",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "from": "Disabled",
          "to": "Enabled",
          "as": "previously-disabled-route"
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
      "text": "Undo progress is retained; eligible original outward-model routing binding rows are restored and protected later bindings are not deleted.",
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
      "target": "internal/store/unify.go#UndoBatch"
    }
  ]
}
---












# Undo name unification batch undone

## Trigger

Select the unification batch to undo.

## Outcome

Undo progress is retained; eligible original route/member rows are restored and protected later bindings are not deleted.


## Edge cases

- A new batch replay is one transaction: a later conflict rolls back its new replay writes. Previously committed single-original restorations stay marked undone and are skipped on later attempts.

- Each reconstructed matcher or binding keeps the Enabled or Disabled choice in its saved snapshot; restoration does not force it enabled.

- Replay in reverse order and skip operations already undone or whose targets disappeared; retain successful undo progress. Same-name reconstruction conflict and protected later bindings refuse destructive replay.

## Decision points

### Recorded operation

Which active operation is being reversed?

- Deleted original → reconstruct original identities and settings, preserving the independent saved enabled choices of model and bindings.
- Created binding → remove only that recorded binding if it remains.
- Created model → remove it only after guarding later manual and other active-batch bindings.
- Enabled or legacy archived model → restore its recorded previous enabled choice in place.

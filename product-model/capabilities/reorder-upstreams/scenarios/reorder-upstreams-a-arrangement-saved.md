---
{
  "kind": "primary",
  "routes": {
    "main": "A arrangement saved"
  },
  "steps": [
    {
      "text": "Supply the ordered granted-upstream choices for a model.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "If no default Routing plan exists, establish it for the current model arrangement before retaining the submitted order.",
      "kind": "product",
      "entities": [
        {
          "entity": "routing-plan",
          "effect": "creates",
          "facts": [
            "Name",
            "Account",
            "Default selection",
            "Model arrangements",
            "Token selections"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Access policy. Consult the Route member.",
      "kind": "condition",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "reads",
          "facts": [
            "Models",
            "All models",
            "Route members",
            "Personal routing"
          ]
        },
        {
          "entity": "route-member",
          "effect": "reads",
          "facts": [
            "Route",
            "Connection",
            "Status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "Save changes to the Routing plan.",
      "kind": "product",
      "entities": [
        {
          "entity": "routing-plan",
          "effect": "changes",
          "facts": [
            "Model arrangements"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    },
    {
      "text": "The arrangement is saved; a missing implicit default can be established as part of the save.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::accessible-models"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/MemberModelsPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/member/RouteOrderDialog.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/team_access.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/team.go"
    }
  ]
}
---









# Reorder upstreams arrangement saved

## Trigger

Supply the ordered granted-member choices for a model.

## Outcome

The arrangement is saved; a missing implicit default can be established as part of the save.


## Decision points

### Default plan existence

Is there a retained default plan when no named plan is selected?

- Existing default or selected named plan → change that plan’s model arrangement.
- No default → create the default, then retain the model arrangement.

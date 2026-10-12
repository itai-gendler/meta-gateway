---
{
  "kind": "primary",
  "routes": {
    "main": "D groups listed"
  },
  "steps": [
    {
      "text": "Read the Token-group inventory.",
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
      "text": "Consult the Token group.",
      "kind": "condition",
      "entities": [
        {
          "entity": "token-group",
          "effect": "reads",
          "facts": [
            "Name",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request rate"
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
      "text": "Group budgets, usage counters and request-rate limits are presented.",
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
      "target": "web/src/team/panels/PricingPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/QuotasPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_usage.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/group.go"
    }
  ]
}
---








# Browse token groups groups listed

## Trigger

Read the Token-group inventory.

## Outcome

Group budgets, usage counters and request-rate limits are presented.

---
{
  "kind": "primary",
  "routes": {
    "main": "D multipliers listed"
  },
  "steps": [
    {
      "text": "Read the multiplier inventory.",
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
      "text": "Consult the Billing multiplier. Consult the Model metadata.",
      "kind": "condition",
      "entities": [
        {
          "entity": "billing-multiplier",
          "effect": "reads",
          "facts": [
            "Model name",
            "Multiplier"
          ]
        },
        {
          "entity": "model-metadata",
          "effect": "reads",
          "facts": [
            "Model name",
            "Price layer"
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
      "text": "Configured multiplier entries and reference values are returned.",
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








# Browse billing multipliers multipliers listed

## Trigger

Read the multiplier inventory.

## Outcome

Configured multiplier entries and reference values are returned.

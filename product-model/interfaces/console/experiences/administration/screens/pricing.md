---
{
  "entities": [
    {
      "entity": "billing-multiplier",
      "shows": [
        "Model name",
        "Multiplier"
      ],
      "collects": [
        "Model name",
        "Multiplier"
      ]
    },
    {
      "entity": "model-metadata",
      "shows": [
        "Model name",
        "Price layer"
      ]
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



# Pricing

Model billing multipliers and reference pricing, distinct from actual persisted charges.

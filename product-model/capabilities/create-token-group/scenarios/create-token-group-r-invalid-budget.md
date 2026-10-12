---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid budget"
  },
  "steps": [
    {
      "text": "Supply name, token/money totals and request rate.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::credit-and-quotas"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A submitted quota or rate value is negative, non-finite or outside the supported range.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::credit-and-quotas"
        }
      }
    },
    {
      "text": "The budget settings are rejected without replacing existing valid values.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::credit-and-quotas"
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








# Create token group invalid budget

## Trigger

A submitted quota or rate value is negative, non-finite or outside the supported range.

## Outcome

The budget settings are rejected without replacing existing valid values.

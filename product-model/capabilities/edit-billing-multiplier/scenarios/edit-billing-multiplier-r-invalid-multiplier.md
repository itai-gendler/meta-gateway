---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid multiplier"
  },
  "steps": [
    {
      "text": "Supply its replacement multiplier.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::pricing"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The multiplier is non-finite, negative or exceeds 1000.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::pricing"
        }
      }
    },
    {
      "text": "The multiplier input is rejected; the existing entry or default one remains.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::pricing"
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








# Edit billing multiplier invalid multiplier

## Trigger

The multiplier is non-finite, negative or exceeds 1000.

## Outcome

The multiplier input is rejected; the existing entry or default one remains.

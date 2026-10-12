---
{
  "kind": "primary",
  "routes": {
    "main": "R multiplier updated"
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
      "text": "Save changes to the Billing multiplier.",
      "kind": "product",
      "entities": [
        {
          "entity": "billing-multiplier",
          "effect": "changes",
          "facts": [
            "Multiplier"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::pricing"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Subsequent booking uses the replacement multiplier; prior charges remain unchanged.",
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








# Edit billing multiplier multiplier updated

## Trigger

Supply its replacement multiplier.

## Outcome

Subsequent booking uses the replacement multiplier; prior charges remain unchanged.

---
{
  "kind": "primary",
  "routes": {
    "main": "R multiplier saved"
  },
  "steps": [
    {
      "text": "Supply model name and multiplier.",
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
      "text": "Establish the Billing multiplier.",
      "kind": "product",
      "entities": [
        {
          "entity": "billing-multiplier",
          "effect": "creates",
          "facts": [
            "Model name",
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
      "text": "The multiplier is saved; the upsert contract does not promise a duplicate-name conflict.",
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








# Create billing multiplier multiplier saved

## Trigger

Supply model name and multiplier.

## Outcome

The multiplier is saved; the upsert contract does not promise a duplicate-name conflict.

---
{
  "kind": "primary",
  "routes": {
    "main": "D multiplier saved"
  },
  "steps": [
    {
      "text": "Supply model name and multiplier.",
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
          "place": "management-api::administration"
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








# Create billing multiplier multiplier saved

## Trigger

Supply model name and multiplier.

## Outcome

The multiplier is saved; the upsert contract does not promise a duplicate-name conflict.

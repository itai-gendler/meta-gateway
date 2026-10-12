---
{
  "kind": "primary",
  "routes": {
    "main": "R default restored"
  },
  "steps": [
    {
      "text": "Select the multiplier to remove.",
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
      "text": "Remove the Billing multiplier.",
      "kind": "product",
      "entities": [
        {
          "entity": "billing-multiplier",
          "effect": "removes"
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
      "text": "Missing-entry default one is restored for subsequent charges.",
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








# Delete billing multiplier default restored

## Trigger

Select the multiplier to remove.

## Outcome

Missing-entry default one is restored for subsequent charges.

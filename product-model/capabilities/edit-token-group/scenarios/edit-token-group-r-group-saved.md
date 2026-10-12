---
{
  "kind": "primary",
  "routes": {
    "main": "R group saved"
  },
  "steps": [
    {
      "text": "Supply replacement totals and request rate.",
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
      "text": "Save changes to the Token group.",
      "kind": "product",
      "entities": [
        {
          "entity": "token-group",
          "effect": "changes",
          "facts": [
            "Name",
            "Token limit",
            "Money limit",
            "Request rate"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::credit-and-quotas"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The shared limits are saved without arbitrary team user counter editing.",
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








# Edit token group group saved

## Trigger

Supply replacement totals and request rate.

## Outcome

The shared limits are saved without arbitrary member counter editing.

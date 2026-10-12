---
{
  "kind": "primary",
  "routes": {
    "main": "R group deleted"
  },
  "steps": [
    {
      "text": "Select a non-default group to remove.",
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
      "text": "Remove the Token group.",
      "kind": "product",
      "entities": [
        {
          "entity": "token-group",
          "effect": "removes"
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
      "text": "The definition is removed; a missing named group resolves without configured quota/rate limits.",
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








# Delete token group group deleted

## Trigger

Select a non-default group to remove.

## Outcome

The definition is removed; a missing named group resolves without configured quota/rate limits.

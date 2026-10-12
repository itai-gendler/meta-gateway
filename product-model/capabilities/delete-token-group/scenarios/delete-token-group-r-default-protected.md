---
{
  "kind": "validation",
  "routes": {
    "main": "R default protected"
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
      "text": "The selected quota group is the protected default definition.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::credit-and-quotas"
        }
      }
    },
    {
      "text": "Deletion is refused and the default definition remains.",
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








# Delete token group default protected

## Trigger

The selected quota group is the protected default definition.

## Outcome

Deletion is refused and the default definition remains.

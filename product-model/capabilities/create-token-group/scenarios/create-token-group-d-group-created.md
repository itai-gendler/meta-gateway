---
{
  "kind": "primary",
  "routes": {
    "main": "D group created"
  },
  "steps": [
    {
      "text": "Supply name, token/money totals and request rate.",
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
      "text": "Establish the Token group.",
      "kind": "product",
      "entities": [
        {
          "entity": "token-group",
          "effect": "creates",
          "facts": [
            "Name",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request rate"
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
      "text": "The named group exists with normalized limits and initial counters.",
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








# Create token group group created

## Trigger

Supply name, token/money totals and request rate.

## Outcome

The named group exists with normalized limits and initial counters.

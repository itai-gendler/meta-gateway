---
{
  "entities": [
    {
      "entity": "token-group",
      "shows": [
        "Name",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used",
        "Request rate"
      ],
      "collects": [
        "Name",
        "Token limit",
        "Money limit",
        "Request rate"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Login name",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ]
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



# Credit and quotas

The Token-group quota subject shows shared pool limits, rates and Account budget information.

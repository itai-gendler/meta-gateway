---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "token-group",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "inference-api"
        }
      ],
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
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "configuredBy": "system-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
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



# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token may read Token group

Deployment administrator and Owner configure Token groups, preserving the protected default group. Inference consults the actual presented Token's applicable group. Transactional booking increments only that group's usage counters as a Product continuation; it does not enable arbitrary customer configuration edits.

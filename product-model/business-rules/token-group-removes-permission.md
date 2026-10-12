---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "token-group",
      "effect": "removes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ],
      "when": [
        {
          "fact": "Name",
          "is-not": "default"
        }
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



# Deployment administrator, Owner may remove Token group

Deployment administrator and Owner configure Token groups, preserving the protected default group. Inference consults the actual presented Token's applicable group. Transactional booking increments only that group's usage counters as a Product continuation; it does not enable arbitrary customer configuration edits.

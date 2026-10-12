---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-billing-multipliers"
    },
    {
      "type": "capability",
      "id": "browse-tokens"
    },
    {
      "type": "capability",
      "id": "browse-request-logs"
    },
    {
      "type": "capability",
      "id": "change-money-display"
    },
    {
      "type": "capability",
      "id": "delete-billing-multiplier"
    },
    {
      "type": "entity",
      "id": "usage-record"
    },
    {
      "type": "entity",
      "id": "money-display-settings"
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



# Recorded charges remain distinct from reference prices and display conversion

Recorded costs versus reference ranges/display conversion; multiplier zero can remove monetary charge without removing token usage; deleting multiplier restores 1

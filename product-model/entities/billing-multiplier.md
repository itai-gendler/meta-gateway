---
{
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
  ],
  "domain": "pricing"
}
---



# Billing multiplier

A model-specific multiplier applied after whole-layer price selection.

## Information kept

- **Model name** — the outward model name identifying metadata, capability or pricing information.
- **Multiplier** — the model billing multiplier; missing pricing entry means one.

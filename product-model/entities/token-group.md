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
  "domain": "credit-and-quotas",
  "relations": [
    {
      "entity": "system-token",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "account-token",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---



# Token group

A named downstream quota and rate pool shared by assigned Tokens.

## Information kept

- **Name** — the Product-facing name identifying this instance.
- **Token limit** — the group token-usage budget; zero means unlimited.
- **Tokens used** — the accumulated recorded token usage, retained until an explicit counter reset.
- **Money limit** — the configured monetary budget in the gateway ledger unit; zero means unlimited.
- **Money used** — the accumulated recorded configured cost in the gateway ledger unit.
- **Request rate** — the configured request-rate limit.

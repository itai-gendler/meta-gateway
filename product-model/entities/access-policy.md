---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ],
  "domain": "access-and-routing",
  "relations": [
    {
      "entity": "account",
      "verb": "governs",
      "cardinality": "one-to-many"
    }
  ]
}
---



# Access policy

The model, member, rate, Token-count and personal-configuration grants assigned to Accounts.

## Information kept

- **Name** — the Product-facing name identifying this instance.
- **All models** — whether the access policy allows model names without an explicit name list.
- **Models** — the explicit model-name grants retained by the access policy.
- **Route members** — the explicit route-member grants retained by the access policy.
- **Token limit** — the configured token-count budget; on an Access policy this means the maximum retained Token count.
- **Request rate** — the configured request-rate limit.
- **Personal routing** — whether the access policy permits personal routing plans.
- **Request preference editing** — whether the access policy permits personal failover/retry preferences.

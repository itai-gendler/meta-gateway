---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/MemberModelsPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/member/RouteOrderDialog.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/team_access.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/team.go"
    }
  ],
  "domain": "models",
  "relations": [
    {
      "entity": "account-token",
      "verb": "is selected by",
      "cardinality": "one-to-many"
    },
    {
      "entity": "route-member",
      "verb": "arranges",
      "cardinality": "many-to-many"
    }
  ]
}
---



# Routing plan

An Account-owned set of model-specific upstream arrangements selected by its Tokens.

## Information kept

- **Name** — the Product-facing name identifying this instance.
- **Account** — the associated Account, without implying current credential eligibility.
- **Default selection** — whether this is the implicit default plan used by Tokens without a named selection.
- **Model arrangements** — model-specific ordered granted bindings, weights and disabled choices.
- **Token selections** — the Tokens currently selecting this plan.

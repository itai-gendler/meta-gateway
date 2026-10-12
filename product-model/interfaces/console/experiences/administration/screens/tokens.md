---
{
  "entities": [
    {
      "entity": "system-token",
      "shows": [
        "Name",
        "Credential",
        "Credential hint",
        "Status",
        "Scopes",
        "Model restrictions",
        "Denylist",
        "IP restrictions",
        "Expiry",
        "Token group",
        "Route group",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ],
      "collects": [
        "Name",
        "Credential",
        "Status",
        "Scopes",
        "Model restrictions",
        "Denylist",
        "IP restrictions",
        "Expiry",
        "Token group",
        "Route group",
        "Token limit",
        "Money limit"
      ]
    },
    {
      "entity": "account-token",
      "shows": [
        "Name",
        "Credential",
        "Credential hint",
        "Status",
        "Scopes",
        "Model restrictions",
        "Denylist",
        "IP restrictions",
        "Expiry",
        "Token group",
        "Route group",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used",
        "Account",
        "Routing plan",
        "Neutralization"
      ],
      "collects": [
        "Name",
        "Credential",
        "Status",
        "Scopes",
        "Model restrictions",
        "Denylist",
        "IP restrictions",
        "Expiry",
        "Token group",
        "Route group",
        "Token limit",
        "Money limit",
        "Account",
        "Routing plan"
      ]
    },
    {
      "entity": "usage-record",
      "shows": [
        "Recorded cost"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Keys.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_keys.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/downstream_key.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    }
  ]
}
---



# Tokens

The downstream credential subject presents privileged settings, budgets, usage and explicit credential-reveal outcomes.

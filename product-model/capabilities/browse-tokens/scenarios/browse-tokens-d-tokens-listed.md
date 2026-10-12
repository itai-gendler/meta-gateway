---
{
  "kind": "primary",
  "routes": {
    "main": "D tokens listed"
  },
  "steps": [
    {
      "text": "Read the appropriate Token inventory.",
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
      "text": "Consult the System token. Consult the Account token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "system-token",
          "effect": "reads",
          "facts": [
            "Name",
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
          ]
        },
        {
          "entity": "account-token",
          "effect": "reads",
          "facts": [
            "Name",
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
      "text": "The selected metadata and recorded cost projection is returned; own lists omit foreign and neutralized records.",
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








# Browse tokens tokens listed

## Trigger

Read the appropriate Token inventory.

## Outcome

The selected metadata and recorded cost projection is returned; own lists omit foreign and neutralized records.

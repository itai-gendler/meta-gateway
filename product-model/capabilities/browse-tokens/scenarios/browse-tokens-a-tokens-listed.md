---
{
  "kind": "primary",
  "routes": {
    "main": "A tokens listed"
  },
  "steps": [
    {
      "text": "Read the appropriate Token inventory.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Account token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account-token",
          "effect": "reads",
          "facts": [
            "Name",
            "Credential hint",
            "Status",
            "Model restrictions",
            "IP restrictions",
            "Expiry",
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
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
    },
    {
      "text": "The selected metadata and recorded cost projection is returned; own lists omit foreign and neutralized records.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
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

---
{
  "kind": "primary",
  "routes": {
    "main": "A token rotated"
  },
  "steps": [
    {
      "text": "Select credential rotation.",
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
      "text": "Save changes to the Account token.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "facts": [
            "Credential",
            "Credential hint"
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
      "text": "New plaintext authority is returned and the previous credential no longer authenticates through this operation.",
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








# Rotate token token rotated

## Trigger

Select credential rotation.

## Outcome

New plaintext authority is returned and the previous credential no longer authenticates through this operation.

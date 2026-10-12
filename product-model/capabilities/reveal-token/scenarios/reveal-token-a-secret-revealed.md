---
{
  "kind": "primary",
  "routes": {
    "main": "A secret revealed"
  },
  "steps": [
    {
      "text": "Select the Token secret reveal.",
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
            "Credential"
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
      "text": "Plaintext authority is returned only when stored encrypted material is available; caller-held hash-only authority can remain independently valid.",
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









# Reveal token secret revealed

## Trigger

Select the Token secret reveal.

## Outcome

Plaintext authority is returned only when stored encrypted material is available; caller-held hash-only authority can remain independently valid.

## Edge cases

- A foreign key is unavailable. A retained credential without decryptable plaintext returns the explicit unavailable result instead of inventing a secret.

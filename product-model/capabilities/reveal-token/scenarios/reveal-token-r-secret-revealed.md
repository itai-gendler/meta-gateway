---
{
  "kind": "primary",
  "routes": {
    "main": "R secret revealed"
  },
  "steps": [
    {
      "text": "Select the Token secret reveal.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      },
      "actor": "owner"
    },
    {
      "text": "For the selected privileged credential, consult the System token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "system-token",
          "effect": "reads",
          "facts": [
            "Credential"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      },
      "actor": "owner"
    },
    {
      "text": "For the selected owned credential, consult the Account token.",
      "kind": "condition",
      "actor": "owner",
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
          "place": "console::administration::tokens"
        }
      }
    },
    {
      "text": "Plaintext authority is returned only when stored encrypted material is available; caller-held hash-only authority can remain independently valid.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
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









# Reveal token secret revealed

## Trigger

Select the Token secret reveal.

## Outcome

Plaintext authority is returned only when stored encrypted material is available; caller-held hash-only authority can remain independently valid.


## Decision points

### Selected downstream credential

Which retained credential was selected through privileged administration? Exactly the selected instance is affected; this does not give personal input privileged-field parity.

- System token → apply the System-token branch.
- Account token → apply the Account-token branch with full administrative authority.

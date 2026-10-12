---
{
  "kind": "primary",
  "routes": {
    "main": "R token rotated"
  },
  "steps": [
    {
      "text": "Select credential rotation.",
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
      "text": "For the selected privileged credential, save changes to the System token.",
      "kind": "product",
      "entities": [
        {
          "entity": "system-token",
          "effect": "changes",
          "facts": [
            "Credential",
            "Credential hint"
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
      "text": "For the selected owned credential, save changes to the Account token.",
      "kind": "product",
      "actor": "owner",
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
          "place": "console::administration::tokens"
        }
      }
    },
    {
      "text": "New plaintext authority is returned and the previous credential no longer authenticates through this operation.",
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









# Rotate token token rotated

## Trigger

Select credential rotation.

## Outcome

New plaintext authority is returned and the previous credential no longer authenticates through this operation.


## Decision points

### Selected downstream credential

Which retained credential was selected through privileged administration? Exactly the selected instance is affected; this does not give personal input privileged-field parity.

- System token → apply the System-token branch.
- Account token → apply the Account-token branch with full administrative authority.

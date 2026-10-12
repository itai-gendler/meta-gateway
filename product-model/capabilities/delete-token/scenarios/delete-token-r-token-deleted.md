---
{
  "kind": "primary",
  "routes": {
    "main": "R token deleted"
  },
  "steps": [
    {
      "text": "Select the Token to delete.",
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
      "text": "For the selected privileged credential, remove the System token.",
      "kind": "product",
      "entities": [
        {
          "entity": "system-token",
          "effect": "removes",
          "from": "Enabled"
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
      "text": "For the selected owned credential, remove the Account token.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "account-token",
          "effect": "removes",
          "from": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      }
    },
    {
      "text": "Privileged deletion removes the record; own deletion disables and replaces retained authority, keeping attribution.",
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









# Delete token token deleted

## Trigger

Select the Token to delete.

## Outcome

Privileged deletion removes the record; own deletion disables and replaces retained authority, keeping attribution.


## Decision points

### Selected downstream credential

Which retained credential was selected through privileged administration? Exactly the selected instance is affected; this does not give personal input privileged-field parity.

- System token → apply the System-token branch.
- Account token → apply the Account-token branch with full administrative authority.

---
{
  "kind": "primary",
  "routes": {
    "main": "D token enabled"
  },
  "steps": [
    {
      "text": "Select the Token to enable.",
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
      "text": "For the selected privileged credential, save changes to the System token in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "system-token",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Enabled",
          "from": "Disabled"
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
      "text": "For the selected owned credential, save changes to the Account token in Enabled state.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Enabled",
          "from": "Disabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      }
    },
    {
      "text": "The enabled state is saved and applicable authentication cache invalidated.",
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









# Enable token token enabled

## Trigger

Select the Token to enable.

## Outcome

The enabled state is saved and applicable authentication cache invalidated.


## Decision points

### Selected downstream credential

Which retained credential was selected through privileged administration? Exactly the selected instance is affected; this does not give personal input privileged-field parity.

- System token → apply the System-token branch.
- Account token → apply the Account-token branch with full administrative authority.

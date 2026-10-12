---
{
  "kind": "primary",
  "routes": {
    "main": "D token disabled"
  },
  "steps": [
    {
      "text": "Select the Token to disable.",
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
      "text": "For the selected privileged credential, save changes to the System token in Disabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "system-token",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Disabled",
          "from": "Enabled"
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
      "text": "For the selected owned credential, save changes to the Account token in Disabled state.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "facts": [
            "Status"
          ],
          "to": "Disabled",
          "from": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      }
    },
    {
      "text": "The disabled state is saved and applicable authentication cache invalidated; disabled own Tokens still consume a creation slot.",
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









# Disable token token disabled

## Trigger

Select the Token to disable.

## Outcome

The disabled state is saved and applicable authentication cache invalidated; disabled own Tokens still consume a creation slot.


## Decision points

### Selected downstream credential

Which retained credential was selected through privileged administration? Exactly the selected instance is affected; this does not give personal input privileged-field parity.

- System token → apply the System-token branch.
- Account token → apply the Account-token branch with full administrative authority.

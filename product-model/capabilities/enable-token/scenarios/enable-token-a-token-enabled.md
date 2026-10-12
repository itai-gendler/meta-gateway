---
{
  "kind": "primary",
  "routes": {
    "main": "A token enabled"
  },
  "steps": [
    {
      "text": "Select the Token to enable.",
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
      "text": "Save changes to the Account token in Enabled state.",
      "kind": "product",
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
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
    },
    {
      "text": "The enabled state is saved and applicable authentication cache invalidated.",
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








# Enable token token enabled

## Trigger

Select the Token to enable.

## Outcome

The enabled state is saved and applicable authentication cache invalidated.

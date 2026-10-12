---
{
  "kind": "primary",
  "routes": {
    "main": "A token deleted"
  },
  "steps": [
    {
      "text": "Select the Token to delete.",
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
      "text": "Save changes to the Account token in Neutralized state.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "to": "Neutralized",
          "facts": [
            "Status",
            "Credential",
            "Credential hint",
            "Neutralization"
          ],
          "from": "Enabled"
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
      "text": "Privileged deletion removes the record; own deletion disables and replaces retained authority, keeping attribution.",
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








# Delete token token deleted

## Trigger

Select the Token to delete.

## Outcome

Privileged deletion removes the record; own deletion disables and replaces retained authority, keeping attribution.

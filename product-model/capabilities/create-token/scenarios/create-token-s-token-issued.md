---
{
  "kind": "primary",
  "routes": {
    "main": "S token issued"
  },
  "steps": [
    {
      "text": "Supply the new credential settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Establish the System token in Enabled state.",
      "kind": "product",
      "entities": [
        {
          "entity": "system-token",
          "effect": "creates",
          "facts": [
            "Name",
            "Credential",
            "Credential hint",
            "Status",
            "Scopes",
            "Model restrictions",
            "Denylist",
            "IP restrictions",
            "Expiry",
            "Token group",
            "Route group",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used"
          ],
          "to": "Enabled"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A new Token and its plaintext authority are returned; only own-field input is accepted in the personal contract.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
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








# Create token token issued

## Trigger

Supply the new credential settings.

## Outcome

A new Token and its plaintext authority are returned; only own-field input is accepted in the personal contract.

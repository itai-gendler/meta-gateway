---
{
  "kind": "primary",
  "routes": {
    "main": "A account shown"
  },
  "steps": [
    {
      "text": "Open current local profile information.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name",
            "Display name",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "The current local profile information is presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ]
}
---








# Read account account shown

## Trigger

Open current Account information.

## Outcome

The current Account information is presented.

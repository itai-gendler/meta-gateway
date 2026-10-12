---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Login name",
        "Display name",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used",
        "Request preferences"
      ],
      "collects": [
        "Password credential",
        "Request preferences"
      ]
    },
    {
      "entity": "account-session",
      "shows": [
        "Account",
        "Created at",
        "Expires at",
        "Current session"
      ]
    },
    {
      "entity": "credit-code",
      "collects": [
        "Code credential"
      ]
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



# Account

The own Account-security subject shows budgets, preferences and revocable browser sessions.

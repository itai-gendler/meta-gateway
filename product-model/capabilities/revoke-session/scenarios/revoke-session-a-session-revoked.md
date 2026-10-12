---
{
  "kind": "primary",
  "routes": {
    "main": "A session revoked"
  },
  "steps": [
    {
      "text": "Select the session to revoke.",
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
      "text": "Consult the Account session.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account-session",
          "effect": "reads",
          "facts": [
            "Account",
            "Current session"
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
      "text": "Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-session",
          "effect": "removes"
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
      "text": "The selected session no longer authenticates.",
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








# Revoke session session revoked

## Trigger

Select the session to revoke.

## Outcome

The selected session no longer authenticates.

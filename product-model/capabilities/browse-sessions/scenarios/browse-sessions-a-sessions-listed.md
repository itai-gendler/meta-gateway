---
{
  "kind": "primary",
  "routes": {
    "main": "A sessions listed"
  },
  "steps": [
    {
      "text": "Read the current session inventory.",
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
            "Created at",
            "Expires at",
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
      "text": "Owned sessions show creation, expiry and current-session information.",
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








# Browse sessions sessions listed

## Trigger

Read the current session inventory.

## Outcome

Up to twenty unexpired owned sessions are listed in descending creation order, with expiry and current-session information.

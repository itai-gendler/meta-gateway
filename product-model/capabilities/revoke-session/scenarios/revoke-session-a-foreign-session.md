---
{
  "kind": "validation",
  "routes": {
    "main": "A foreign session"
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
      "text": "The selected session does not belong to the requesting local profile.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      }
    },
    {
      "text": "The selected session is not revoked and the boundary returns its not-found/refusal outcome.",
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








# Revoke session foreign session

## Trigger

The selected session does not belong to the requesting Account.

## Outcome

The selected session is not revoked and the boundary returns its not-found/refusal outcome.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account-session",
      "effect": "creates",
      "contexts": [
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "account"
    },
    {
      "configuredBy": "oauth-settings"
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



# Execution under Account or execution under OAuth settings may create Account session

The Product establishes a cookie session for the Account whose authentication completed. Related Member and Owner role holders list or revoke their own sessions. Full administrators manage sessions, while Administrator revocation is limited to managed Member targets. Password recovery and authorized Account or mode changes invalidate the corresponding sessions as continuations; local operator-credential sign-out does not imply this server operation.

---
{
  "kind": "primary",
  "routes": {
    "main": "L account password"
  },
  "steps": [
    {
      "text": "Supply the chosen sign-in method and its credentials.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::entry"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Account. Consult the Team settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name",
            "Password credential",
            "Status",
            "Session revision"
          ]
        },
        {
          "entity": "team-settings",
          "effect": "reads",
          "facts": [
            "Operating mode"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::entry"
        }
      },
      "actor": "member"
    },
    {
      "text": "Establish the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-session",
          "effect": "creates",
          "facts": [
            "Account",
            "Created at",
            "Expires at",
            "Session credential",
            "Session revision",
            "Current session"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::entry"
        }
      },
      "actor": "member"
    },
    {
      "text": "local profile-password sign-in in Team mode establishes the browser session; failed local profile authentication does not fall back to deployment credentials.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::entry"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/session.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team.go"
    }
  ]
}
---








# Sign in account password

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

Account-password sign-in in Team mode establishes the Account session; failed Account authentication does not fall back to deployment credentials.

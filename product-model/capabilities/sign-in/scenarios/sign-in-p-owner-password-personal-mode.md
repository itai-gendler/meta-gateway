---
{
  "kind": "primary",
  "routes": {
    "main": "P owner password personal mode"
  },
  "steps": [
    {
      "text": "Supply the chosen sign-in method and its credentials.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Account. Consult the full-administration role holder. Consult the Team settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name",
            "Password credential",
            "Status"
          ]
        },
        {
          "entity": "owner",
          "effect": "reads",
          "facts": [
            "Account association"
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
          "place": "console::entry::login"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Establish the Operator session.",
      "kind": "product",
      "entities": [
        {
          "entity": "operator-session",
          "effect": "creates",
          "facts": [
            "Credential",
            "Expires at"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The existing full-administration role holder authenticates by local profile password in Personal mode and receives an operator credential.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "owner"
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








# Sign in owner password personal mode

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

The existing Owner authenticates by Account password in Personal mode and receives an operator credential.

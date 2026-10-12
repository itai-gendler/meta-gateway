---
{
  "kind": "edge",
  "routes": {
    "main": "P oauth provider failure"
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
      "actor": "member"
    },
    {
      "text": "The configured provider fails token/user-information exchange.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      }
    },
    {
      "text": "Sign-in returns the external-provider failure without establishing a new session or invented identity.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
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








# Sign in oauth provider failure

## Trigger

The configured provider fails token/user-information exchange.

## Outcome

Sign-in returns the external-provider failure without establishing a new session or invented identity.

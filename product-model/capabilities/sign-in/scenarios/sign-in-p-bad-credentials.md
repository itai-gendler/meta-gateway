---
{
  "kind": "validation",
  "routes": {
    "main": "P bad credentials"
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
      "text": "The presented sign-in credentials fail their selected principal branch.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      }
    },
    {
      "text": "Sign-in is refused; failure of an existing local profile password does not fall back to deployment authentication.",
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








# Sign in bad credentials

## Trigger

The presented sign-in credentials fail their selected principal branch.

## Outcome

Sign-in is refused; failure of an existing Account password does not fall back to deployment authentication.

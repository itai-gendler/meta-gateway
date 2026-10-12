---
{
  "kind": "validation",
  "routes": {
    "main": "P oauth state"
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
      "text": "The callback does not match the signed OAuth state/PKCE flow.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      }
    },
    {
      "text": "The callback is refused and no binding or session is established.",
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








# Sign in oauth state

## Trigger

The callback does not match the signed OAuth state/PKCE flow.

## Outcome

The callback is refused and no binding or session is established.

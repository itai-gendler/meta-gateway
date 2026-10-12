---
{
  "entities": [
    {
      "entity": "team-settings",
      "shows": [
        "Name",
        "Logo",
        "Notice",
        "Sign-in description"
      ]
    },
    {
      "entity": "operator-settings",
      "shows": [
        "Login name",
        "Second factor enabled",
        "Token-login availability"
      ],
      "collects": [
        "Deployment credential"
      ]
    },
    {
      "entity": "oauth-settings",
      "shows": [
        "Enabled providers"
      ]
    },
    {
      "entity": "account",
      "collects": [
        "Login name",
        "Password credential"
      ]
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



# Login

The entry process presents available sign-in methods and accepts the relevant credentials.

---
{
  "availability": [
    {
      "place": "console::administration"
    },
    {
      "place": "console::personal"
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



# Sign out

Forget the current browser credential and leave the signed-in workspace.

The browser clears its credential and navigation metadata immediately. Account-cookie sign-out also attempts current-session logout; a successful response removes that server session. Logout failure is ignored locally. Signed operator credentials are forgotten locally without global revocation. Browser-origin conversation and image history is retained.

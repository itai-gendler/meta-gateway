---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in"
    },
    {
      "type": "capability",
      "id": "read-account"
    },
    {
      "type": "capability",
      "id": "change-password"
    },
    {
      "type": "capability",
      "id": "browse-sessions"
    },
    {
      "type": "capability",
      "id": "revoke-session"
    },
    {
      "type": "entity",
      "id": "account-session"
    },
    {
      "type": "entity",
      "id": "account"
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



# Account sessions require current Account validity and the session contract

Account-session establishment requires an active Account in Team mode. Use requires the current retained session row, its unexpired deadline and matching security revision. The personal browser contract uses cookies and the applicable CSRF checks; an Authorization header is not substituted for that contract.

---
{
  "entities": [
    {
      "entity": "invitation-code",
      "shows": [
        "Assigned role",
        "Policy",
        "Validity"
      ],
      "collects": [
        "Code credential"
      ]
    },
    {
      "entity": "account",
      "collects": [
        "Login name",
        "Display name",
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



# Invitation registration

The invitation acceptance process shows assignment and validity before creating the invited Account.

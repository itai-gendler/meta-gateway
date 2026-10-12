---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Login name",
        "Display name",
        "Status",
        "Policy",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used",
        "Request preferences",
        "Token count"
      ],
      "collects": [
        "Login name",
        "Display name",
        "Status",
        "Password credential",
        "Policy",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ]
    },
    {
      "entity": "owner",
      "shows": [
        "Account association"
      ]
    },
    {
      "entity": "administrator",
      "shows": [
        "Account association"
      ],
      "collects": [
        "Account association"
      ]
    },
    {
      "entity": "member",
      "shows": [
        "Account association"
      ],
      "collects": [
        "Account association"
      ]
    },
    {
      "entity": "access-policy",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "third-party-identity",
      "shows": [
        "Provider",
        "Subject",
        "Account",
        "Profile name",
        "Email",
        "Last sign-in"
      ]
    },
    {
      "entity": "account-session",
      "shows": [
        "Account",
        "Created at",
        "Expires at",
        "Current session"
      ]
    },
    {
      "entity": "recovery-link",
      "shows": [
        "Account",
        "Validity",
        "Consumption",
        "Revocation"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---



# Members

The staff Account subject shows held-role associations, policies, sessions, identities and budget information.

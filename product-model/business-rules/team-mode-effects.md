---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-team-mode"
    },
    {
      "type": "entity",
      "id": "team-settings"
    },
    {
      "type": "entity",
      "id": "account-session"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/ModePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/OAuthPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth_admin.go"
    }
  ]
}
---



# Team mode changes access without deleting retained Accounts and Tokens

Mode changes: first Owner can be established; disabling retains Accounts/plans/Tokens, clears Account sessions, and changes team-key eligibility

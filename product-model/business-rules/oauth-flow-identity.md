---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in"
    },
    {
      "type": "capability",
      "id": "change-oauth-settings"
    },
    {
      "type": "entity",
      "id": "third-party-identity"
    },
    {
      "type": "entity",
      "id": "oauth-settings"
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



# OAuth binding follows signed flow state and configured registration

OAuth binding: signed state/PKCE, subject uniqueness/reuse, configured registration; blank secret preserves, blank client identity removes provider

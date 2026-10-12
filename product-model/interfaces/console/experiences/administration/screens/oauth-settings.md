---
{
  "entities": [
    {
      "entity": "oauth-settings",
      "shows": [
        "Providers",
        "Enabled providers",
        "Client identity",
        "Client secret availability",
        "Endpoints",
        "Registration",
        "Default policy"
      ],
      "collects": [
        "Client identity",
        "Endpoints",
        "Registration",
        "Default policy"
      ]
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



# OAuth settings

The external sign-in configuration subject shows provider choices and secret availability.

---
{
  "entities": [
    {
      "entity": "team-settings",
      "shows": [
        "Name",
        "Logo",
        "Notice",
        "Sign-in description",
        "API address",
        "Usage visibility",
        "Routing visibility"
      ],
      "collects": [
        "Name",
        "Logo",
        "Notice",
        "Sign-in description",
        "API address",
        "Usage visibility",
        "Routing visibility"
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



# Branding

The team information subject shows member-facing content and feature visibility choices.

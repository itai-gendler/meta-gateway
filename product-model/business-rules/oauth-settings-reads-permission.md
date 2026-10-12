---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "oauth-settings",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        }
      ],
      "facts": [
        "Providers",
        "Enabled providers",
        "Client identity",
        "Client secret availability",
        "Endpoints",
        "Registration",
        "Default policy"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "configuredBy": "oauth-settings"
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



# Deployment administrator, Owner or execution under OAuth settings may read OAuth settings

Deployment administrator and Owner configure OAuth providers and registration settings. Entry processes read configured provider choices and use the actual configured registration authority. A blank secret preserves the stored secret; a blank client identity removes that provider.

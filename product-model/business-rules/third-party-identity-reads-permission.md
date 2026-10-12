---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "third-party-identity",
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
        }
      ],
      "facts": [
        "Provider",
        "Subject",
        "Account",
        "Profile name",
        "Email",
        "Last sign-in"
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
      "actors": [
        "administrator"
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



# Deployment administrator, Owner or Administrator or execution under OAuth settings may read Third party identity

The configured OAuth flow creates or reuses the authenticated provider/subject binding and updates its supported profile observations. Deployment administrator, Owner and Administrator can read or unlink bindings through the inspected staff handlers; those handlers do not apply the general managed-Member target guard.

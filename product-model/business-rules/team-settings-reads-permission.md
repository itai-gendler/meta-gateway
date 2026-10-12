---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-settings",
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
        },
        {
          "place": "console::personal"
        },
        {
          "place": "inference-api"
        }
      ],
      "facts": [
        "Operating mode",
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
      "actors": [
        "member"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
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



# Deployment administrator, Owner or Administrator or Member or Gateway client using Account token or execution under OAuth settings may read Team settings

Full administrators change Team settings. Entry, Account and inference processes consult the safe branding, operating-mode and visibility values relevant to their own contract; these reads do not disclose deployment secrets.

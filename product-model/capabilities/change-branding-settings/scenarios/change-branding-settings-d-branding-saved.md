---
{
  "kind": "primary",
  "routes": {
    "main": "D branding saved"
  },
  "steps": [
    {
      "text": "Supply the branding and visibility settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Team settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "team-settings",
          "effect": "changes",
          "facts": [
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The configured team user-facing information and visibility choices are saved.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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








# Change branding settings branding saved

## Trigger

Supply the branding and visibility settings.

## Outcome

The configured member-facing information and visibility choices are saved.

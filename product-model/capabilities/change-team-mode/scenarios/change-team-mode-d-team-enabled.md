---
{
  "kind": "primary",
  "routes": {
    "main": "D team enabled"
  },
  "steps": [
    {
      "text": "Choose the operating mode.",
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
            "Operating mode"
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
      "text": "Team mode is saved. Existing full-administration role holder association is retained; if absent, first-full-administration role holder establishment uses deployment authority.",
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








# Change team mode team enabled

## Trigger

Choose the operating mode.

## Outcome

Team mode is saved. Existing Owner association is retained; if absent, first-owner establishment uses deployment authority.

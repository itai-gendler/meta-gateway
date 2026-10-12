---
{
  "entities": [
    {
      "entity": "team-settings",
      "shows": [
        "Operating mode"
      ],
      "collects": [
        "Operating mode"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Status",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ]
    },
    {
      "entity": "usage-record",
      "shows": [
        "Tokens",
        "Recorded cost"
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



# Team overview

The team overview presents the operating mode and Account/usage summaries.

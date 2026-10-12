---
{
  "kind": "primary",
  "routes": {
    "main": "D personal enabled"
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
      "text": "Save changes to the Team settings. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "team-settings",
          "effect": "changes",
          "facts": [
            "Operating mode"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
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
      "text": "Personal mode is saved, local profile sessions are cleared, retained local profiles/plans/Tokens remain, and team-key admission fails the mode check.",
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








# Change team mode personal enabled

## Trigger

Choose the operating mode.

## Outcome

Personal mode is saved, Account sessions are cleared, retained Accounts/plans/Tokens remain, and team-key admission fails the mode check.

---
{
  "kind": "primary",
  "routes": {
    "main": "R identity unlinked"
  },
  "steps": [
    {
      "text": "Select the provider identity on the staff local profile subject.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Remove the Third party identity.",
      "kind": "product",
      "entities": [
        {
          "entity": "third-party-identity",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The identity binding is removed without deleting the local profile.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
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








# Unlink identity identity unlinked

## Trigger

Select the provider identity on the staff Account subject.

## Outcome

The identity binding is removed without deleting the Account.

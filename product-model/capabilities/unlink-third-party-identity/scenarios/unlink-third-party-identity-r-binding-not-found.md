---
{
  "kind": "edge",
  "routes": {
    "main": "R binding not found"
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
      "text": "The selected identity binding no longer exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      }
    },
    {
      "text": "Unlinking returns its not-found result without changing the local profile.",
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








# Unlink identity binding not found

## Trigger

The selected identity binding no longer exists.

## Outcome

Unlinking returns its not-found result without changing the Account.

---
{
  "kind": "validation",
  "routes": {
    "main": "A preferences disabled"
  },
  "steps": [
    {
      "text": "Supply failover and retry choices.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "The current policy disables request-preference editing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      }
    },
    {
      "text": "Preference saving is refused and retained preferences are not changed.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ]
}
---








# Change request preferences preferences disabled

## Trigger

The current policy disables request-preference editing.

## Outcome

Preference saving is refused and retained preferences are not changed.

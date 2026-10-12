---
{
  "kind": "primary",
  "routes": {
    "main": "D account paused"
  },
  "steps": [
    {
      "text": "Select the local profile or permitted selected local profiles to pause.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Save changes to the Account in Paused state. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Status",
            "Session revision"
          ],
          "to": "Paused",
          "from": "Active"
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
      "actor": "administrator"
    },
    {
      "text": "The local profile is paused and prior sessions no longer authenticate.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---








# Pause account account paused

## Trigger

Select the Account or permitted selected Accounts to pause.

## Outcome

The Account is paused and prior sessions no longer authenticate.

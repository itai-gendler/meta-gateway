---
{
  "kind": "primary",
  "routes": {
    "main": "D account resumed"
  },
  "steps": [
    {
      "text": "Select the local profile or permitted selected local profiles to resume.",
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
      "text": "Save changes to the Account in Active state. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Status",
            "Session revision"
          ],
          "to": "Active",
          "from": "Paused"
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
      "text": "The local profile is active and the operation applies its security revision/session effects.",
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








# Resume account account resumed

## Trigger

Select the Account or permitted selected Accounts to resume.

## Outcome

The Account is active and the operation applies its security revision/session effects.

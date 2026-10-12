---
{
  "kind": "primary",
  "routes": {
    "main": "D counters reset"
  },
  "steps": [
    {
      "text": "Select the local profile counter reset.",
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
      "text": "Save changes to the Account. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Tokens used",
            "Money used",
            "Session revision"
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
      "actor": "administrator"
    },
    {
      "text": "The recorded local profile counters are reset and the individual-update session effects apply.",
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








# Reset account usage counters reset

## Trigger

Select the Account counter reset.

## Outcome

The recorded Account counters are reset and the individual-update session effects apply.

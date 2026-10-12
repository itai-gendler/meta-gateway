---
{
  "kind": "edge",
  "routes": {
    "main": "R partial import"
  },
  "steps": [
    {
      "text": "Supply the team user import material and assignments.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Supported input contains both valid and individually skipped/invalid entries.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      }
    },
    {
      "text": "Establish the Account in Active state. Establish the Member.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Login name",
            "Display name",
            "Status",
            "Password credential",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences",
            "Token count",
            "Session revision"
          ],
          "to": "Active",
          "with": "member"
        },
        {
          "entity": "member",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Valid items are applied and per-item skipped/error information is returned; whole-document atomicity is not promised.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
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








# Import accounts partial import

## Trigger

Supported input contains both valid and individually skipped/invalid entries.

## Outcome

Valid items are applied and per-item skipped/error information is returned; whole-document atomicity is not promised.

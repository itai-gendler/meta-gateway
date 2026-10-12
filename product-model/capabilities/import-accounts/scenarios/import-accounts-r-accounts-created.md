---
{
  "kind": "primary",
  "routes": {
    "main": "R accounts created"
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
      "text": "Consult the Access policy.",
      "kind": "condition",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "Valid entries become local profiles with role associations; each entry has an outcome.",
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








# Import accounts accounts created

## Trigger

Supply the member import material and assignments.

## Outcome

Valid entries become Accounts with role associations; each entry has an outcome.

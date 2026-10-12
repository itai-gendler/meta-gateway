---
{
  "kind": "primary",
  "routes": {
    "main": "R account created"
  },
  "steps": [
    {
      "text": "Supply login/display name, password choice, policy, role assignment and budgets.",
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
      "text": "The local profile is created and its chosen fixed-role association established; generated password material is returned once.",
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








# Create account account created

## Trigger

Supply login/display name, password choice, policy, role assignment and budgets.

## Outcome

The Account is created and its chosen fixed-role association established; generated password material is returned once.

---
{
  "kind": "primary",
  "routes": {
    "main": "R accounts listed"
  },
  "steps": [
    {
      "text": "Read the permitted local profile roster.",
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
      "text": "Consult the Account. Consult the Member. Consult the Administrator. Consult the full-administration role holder.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name",
            "Display name",
            "Status",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Token count"
          ]
        },
        {
          "entity": "member",
          "effect": "reads",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "administrator",
          "effect": "reads",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "owner",
          "effect": "reads",
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
      "text": "The staff roster is presented within the principal's target scope.",
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








# Browse accounts accounts listed

## Trigger

Read the permitted Account roster.

## Outcome

The staff roster is presented within the principal's target scope.

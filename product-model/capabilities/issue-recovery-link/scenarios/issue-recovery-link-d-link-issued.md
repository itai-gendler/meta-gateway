---
{
  "kind": "primary",
  "routes": {
    "main": "D link issued"
  },
  "steps": [
    {
      "text": "Select the target local profile.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Revoke any previous Recovery link for the selected subject.",
      "kind": "product",
      "entities": [
        {
          "entity": "recovery-link",
          "effect": "changes",
          "as": "previous-authority",
          "facts": [
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Establish the Recovery link.",
      "kind": "product",
      "entities": [
        {
          "entity": "recovery-link",
          "effect": "creates",
          "facts": [
            "Code credential",
            "Account",
            "Validity",
            "Consumption",
            "Revocation"
          ],
          "as": "new-authority"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A new recovery credential is returned, replacing applicable previous recovery authority.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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








# Issue recovery link link issued

## Trigger

Select the target Account.

## Outcome

A new recovery credential is returned, replacing applicable previous recovery authority.

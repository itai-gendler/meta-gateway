---
{
  "kind": "primary",
  "routes": {
    "main": "D bulk policy assigned"
  },
  "steps": [
    {
      "text": "Supply profile/password/policy edits or a selected local profile set and policy.",
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
      "text": "Save changes to the Account.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Policy"
          ]
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
      "text": "The selected permitted local profiles receive the new policy; this bulk path does not increment their session revision or delete sessions.",
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








# Edit account profile bulk policy assigned

## Trigger

Supply profile/password/policy edits or a selected Account set and policy.

## Outcome

The selected permitted Accounts receive the new policy; this bulk path does not increment their session revision or delete sessions.

---
{
  "kind": "primary",
  "routes": {
    "main": "D policy deleted"
  },
  "steps": [
    {
      "text": "Select the policy to remove.",
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
      "text": "Remove the Access policy.",
      "kind": "product",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "removes"
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
      "text": "The policy is removed without deleting or silently reassigning referenced local profiles.",
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








# Delete access policy policy deleted

## Trigger

Select the policy to remove.

## Outcome

The policy is removed without deleting or silently reassigning referenced Accounts.

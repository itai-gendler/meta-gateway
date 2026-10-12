---
{
  "kind": "edge",
  "routes": {
    "main": "R policy in use"
  },
  "steps": [
    {
      "text": "Select the policy to remove.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The selected policy is default-protected or still referenced by local profiles.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
        }
      }
    },
    {
      "text": "Deletion reports its conflict/protection outcome and does not silently reassign those local profiles.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
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








# Delete access policy policy in use

## Trigger

The selected policy is default-protected or still referenced by Accounts.

## Outcome

Deletion reports its conflict/protection outcome and does not silently reassign those Accounts.

---
{
  "kind": "validation",
  "routes": {
    "main": "R owner required"
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
      "actor": "administrator"
    },
    {
      "text": "The operation is submitted by a limited staff principal rather than a full administrative principal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
        }
      }
    },
    {
      "text": "The operation returns full-administration role holder-required without its requested mutation.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
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








# Delete access policy owner required

## Trigger

The operation is submitted by an Administrator rather than a full administrative principal.

## Outcome

The operation returns owner-required without its requested mutation.

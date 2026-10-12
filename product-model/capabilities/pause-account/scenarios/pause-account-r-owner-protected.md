---
{
  "kind": "validation",
  "routes": {
    "main": "R owner protected"
  },
  "steps": [
    {
      "text": "Select the local profile or permitted selected local profiles to pause.",
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
      "text": "The requested role reassignment or pause targets the protected full-administration role holder association.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      }
    },
    {
      "text": "The operation is refused and the full-administration role holder association/active choice is retained.",
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








# Pause account owner protected

## Trigger

The requested role reassignment or pause targets the protected Owner association.

## Outcome

The operation is refused and the Owner association/active choice is retained.

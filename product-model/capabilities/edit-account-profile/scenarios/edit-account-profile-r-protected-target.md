---
{
  "kind": "validation",
  "routes": {
    "main": "R protected target"
  },
  "steps": [
    {
      "text": "Supply profile/password/policy edits or a selected local profile set and policy.",
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
      "text": "A staff profile update targets an local profile outside its managed-target scope.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      }
    },
    {
      "text": "The update is refused and the target retains its saved profile/security information.",
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








# Edit account profile protected target

## Trigger

A staff profile update targets an Account outside its managed-target scope.

## Outcome

The update is refused and the target retains its saved profile/security information.

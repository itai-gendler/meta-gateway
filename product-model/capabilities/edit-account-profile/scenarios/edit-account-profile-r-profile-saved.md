---
{
  "kind": "primary",
  "routes": {
    "main": "R profile saved"
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
      "text": "Save changes to the Account. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Display name",
            "Policy",
            "Session revision"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
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
      "text": "Profile or policy information is saved; individual update and bulk policy assignment retain different session effects.",
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








# Edit account profile profile saved

## Trigger

Supply profile/password/policy edits or a selected Account set and policy.

## Outcome

Profile or policy information is saved; individual update and bulk policy assignment retain different session effects.

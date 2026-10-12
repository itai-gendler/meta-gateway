---
{
  "kind": "primary",
  "routes": {
    "main": "D sessions revoked"
  },
  "steps": [
    {
      "text": "Select an local profile and revoke its sessions.",
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
      "actor": "administrator"
    },
    {
      "text": "Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-session",
          "effect": "removes"
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
      "text": "Sessions are deleted; explicit bulk revocation need not increment local profile revision.",
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








# Revoke account sessions sessions revoked

## Trigger

Select an Account and revoke its sessions.

## Outcome

Sessions are deleted; explicit bulk revocation need not increment Account revision.

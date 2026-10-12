---
{
  "kind": "primary",
  "routes": {
    "main": "D code revoked"
  },
  "steps": [
    {
      "text": "Select the code to revoke.",
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
      "text": "For a selected Invitation code, save its revocation choice.",
      "kind": "product",
      "entities": [
        {
          "entity": "invitation-code",
          "effect": "changes",
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
      "actor": "administrator"
    },
    {
      "text": "For a selected Credit code, save its revocation choice.",
      "kind": "product",
      "entities": [
        {
          "entity": "credit-code",
          "effect": "changes",
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
      "actor": "administrator"
    },
    {
      "text": "The code is retained with further use revoked.",
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
      "target": "web/src/team/CodePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go"
    }
  ]
}
---









# Revoke code code revoked

## Trigger

Select the code to revoke.

## Outcome

The code is retained with further use revoked.


## Decision points

### Selected code purpose

Which retained code is selected? Only that code is revoked.

- Invitation → retain its assignment and consumed uses while revoking further registration.
- Credit → retain its face values and redemptions while revoking further redemption.

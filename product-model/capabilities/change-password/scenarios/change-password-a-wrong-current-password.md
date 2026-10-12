---
{
  "kind": "validation",
  "routes": {
    "main": "A wrong current password"
  },
  "steps": [
    {
      "text": "Supply current and replacement passwords.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "The supplied current password does not verify.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      }
    },
    {
      "text": "Password replacement is refused without changing the stored password.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ]
}
---








# Change password wrong current password

## Trigger

The supplied current password does not verify.

## Outcome

Password replacement is refused without changing the stored password.

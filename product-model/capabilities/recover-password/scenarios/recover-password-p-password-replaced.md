---
{
  "kind": "primary",
  "routes": {
    "main": "P password replaced"
  },
  "steps": [
    {
      "text": "Supply the recovery credential and replacement password.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::password-recovery"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Recovery link.",
      "kind": "condition",
      "entities": [
        {
          "entity": "recovery-link",
          "effect": "reads",
          "facts": [
            "Account",
            "Validity",
            "Consumption",
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::password-recovery"
        }
      },
      "actor": "member"
    },
    {
      "text": "Save changes to the Account. Save changes to the Recovery link. Remove the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password credential",
            "Session revision"
          ]
        },
        {
          "entity": "recovery-link",
          "effect": "changes",
          "facts": [
            "Consumption"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::password-recovery"
        }
      },
      "actor": "member"
    },
    {
      "text": "The password is replaced, recovery authority consumed and prior local profile sessions invalidated.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::password-recovery"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/session.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team.go"
    }
  ]
}
---








# Recover password password replaced

## Trigger

Supply the recovery credential and replacement password.

## Outcome

The password is replaced, recovery authority consumed and prior Account sessions invalidated.

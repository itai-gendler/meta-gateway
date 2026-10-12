---
{
  "kind": "primary",
  "routes": {
    "main": "P invitation accepted"
  },
  "steps": [
    {
      "text": "Supply the invitation and a new login name, display name and password.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Invitation code.",
      "kind": "condition",
      "entities": [
        {
          "entity": "invitation-code",
          "effect": "reads",
          "facts": [
            "Assigned role",
            "Policy",
            "Initial tokens",
            "Initial money",
            "Validity",
            "Use limit",
            "Uses",
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
        }
      },
      "actor": "member"
    },
    {
      "text": "Establish the Account in Active state. Save changes to the Invitation code. Establish the Member.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Login name",
            "Display name",
            "Status",
            "Password credential",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences",
            "Token count",
            "Session revision"
          ],
          "to": "Active",
          "with": "member"
        },
        {
          "entity": "invitation-code",
          "effect": "changes",
          "facts": [
            "Uses"
          ]
        },
        {
          "entity": "member",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
        }
      },
      "actor": "member"
    },
    {
      "text": "The invited local profile and its assigned role association exist, with the invitation use consumed.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
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








# Register account invitation accepted

## Trigger

Supply the invitation and a new login name, display name and password.

## Outcome

The invited Account and its assigned role association exist, with the invitation use consumed.

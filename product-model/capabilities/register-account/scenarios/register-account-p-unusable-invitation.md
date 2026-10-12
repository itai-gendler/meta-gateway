---
{
  "kind": "validation",
  "routes": {
    "main": "P unusable invitation"
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
      "text": "The presented invitation is missing, revoked, expired or exhausted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
        }
      }
    },
    {
      "text": "Registration is refused without creating an local profile or consuming an invalid invitation.",
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








# Register account unusable invitation

## Trigger

The presented invitation is missing, revoked, expired or exhausted.

## Outcome

Registration is refused without creating an Account or consuming an invalid invitation.

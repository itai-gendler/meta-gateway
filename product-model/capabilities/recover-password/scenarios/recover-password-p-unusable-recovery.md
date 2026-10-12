---
{
  "kind": "validation",
  "routes": {
    "main": "P unusable recovery"
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
      "text": "The presented local profile-bound recovery authority is missing, revoked, expired or consumed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::password-recovery"
        }
      }
    },
    {
      "text": "Password replacement is refused and the existing password remains.",
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








# Recover password unusable recovery

## Trigger

The presented Account-bound recovery authority is missing, revoked, expired or consumed.

## Outcome

Password replacement is refused and the existing password remains.

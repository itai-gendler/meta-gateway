---
{
  "kind": "edge",
  "routes": {
    "main": "P name conflict"
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
      "text": "The requested name conflicts with an existing protected or applicable resource.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::invitation-registration"
        }
      }
    },
    {
      "text": "The operation returns its name-conflict outcome and does not overwrite the existing identity.",
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








# Register account name conflict

## Trigger

The requested name conflicts with an existing protected or applicable resource.

## Outcome

The operation returns its name-conflict outcome and does not overwrite the existing identity.

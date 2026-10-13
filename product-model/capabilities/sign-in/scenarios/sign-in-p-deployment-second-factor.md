---
{
  "kind": "primary",
  "routes": {
    "main": "P deployment second factor"
  },
  "steps": [
    {
      "text": "Supply the chosen sign-in method and its credentials.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "Consult the deployment configuration.",
      "kind": "condition",
      "entities": [
        {
          "entity": "operator-settings",
          "effect": "reads",
          "facts": [
            "Deployment credential",
            "Token-login availability",
            "Second factor enabled",
            "Owner claim"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "Supply the current second-factor code.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "Establish the Operator session.",
      "kind": "product",
      "entities": [
        {
          "entity": "operator-session",
          "effect": "creates",
          "facts": [
            "Credential",
            "Expires at"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "After password and current second-factor verification, the signed operator credential is returned.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "deployment-administrator"
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








# Sign in deployment second factor

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

After password and current second-factor verification, the signed operator credential is returned.

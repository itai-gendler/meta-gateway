---
{
  "kind": "primary",
  "routes": {
    "main": "L deployment password"
  },
  "steps": [
    {
      "text": "Supply the chosen sign-in method and its credentials.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::entry"
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
          "place": "management-api::entry"
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
          "place": "management-api::entry"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "Deployment password sign-in establishes a signed operator credential without a second-factor prompt.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::entry"
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








# Sign in deployment password

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

Deployment password sign-in establishes a signed operator credential without a second-factor prompt.

---
{
  "kind": "primary",
  "routes": {
    "main": "P oauth existing"
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
      "actor": "member"
    },
    {
      "text": "Consult the OAuth settings. Consult the Third party identity. Consult the Account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "oauth-settings",
          "effect": "reads",
          "facts": [
            "Enabled providers",
            "Endpoints",
            "Client identity"
          ]
        },
        {
          "entity": "third-party-identity",
          "effect": "reads",
          "facts": [
            "Provider",
            "Subject",
            "Account"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Status",
            "Session revision"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "member"
    },
    {
      "text": "Save changes to the Third party identity. Establish the Account session.",
      "kind": "product",
      "entities": [
        {
          "entity": "third-party-identity",
          "effect": "changes",
          "facts": [
            "Profile name",
            "Email",
            "Last sign-in"
          ]
        },
        {
          "entity": "account-session",
          "effect": "creates",
          "facts": [
            "Account",
            "Created at",
            "Expires at",
            "Session credential",
            "Session revision",
            "Current session"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::entry::login"
        }
      },
      "actor": "member"
    },
    {
      "text": "The configured provider subject reuses its existing local profile binding and establishes its browser session.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::entry::login"
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








# Sign in oauth existing

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

The configured provider subject reuses its existing Account binding and establishes its Account session.

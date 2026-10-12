---
{
  "kind": "primary",
  "routes": {
    "main": "P oauth registration"
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
      "text": "Consult the OAuth settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "oauth-settings",
          "effect": "reads",
          "facts": [
            "Enabled providers",
            "Endpoints",
            "Registration",
            "Default policy"
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
      "text": "Establish the Account in Active state. Establish the Member. Establish the Third party identity. Establish the Account session.",
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
          "entity": "member",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "third-party-identity",
          "effect": "creates",
          "facts": [
            "Provider",
            "Subject",
            "Account",
            "Profile name",
            "Email",
            "Last sign-in"
          ],
          "with": "account"
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
          ],
          "with": "account"
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
      "text": "An unbound provider subject under enabled registration establishes a team user local profile, unique identity binding and browser session.",
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








# Sign in oauth registration

## Trigger

Supply the chosen sign-in method and its credentials.

## Outcome

An unbound provider subject under enabled registration establishes a Member Account, unique identity binding and Account session.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account-session",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::personal"
        },
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
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
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "member"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "owner"
        }
      ]
    },
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "actors": [
        "administrator"
      ],
      "when": [
        {
          "entity": "member",
          "fact": "Account association",
          "present": true
        }
      ]
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




# The related Member or the related Owner or Deployment administrator, Owner or Administrator may read Account session

The Product establishes a cookie session for the Account whose authentication completed. Related Member and Owner role holders list or revoke their own sessions. Full administrators manage sessions, while Administrator revocation is limited to managed Member targets. Password recovery and authorized Account or mode changes invalidate the corresponding sessions as continuations; local operator-credential sign-out does not imply this server operation.

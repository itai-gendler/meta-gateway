---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        },
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        },
        {
          "place": "inference-api"
        }
      ],
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
      ]
    }
  ],
  "permits": [
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
    },
    {
      "related": [
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
          "entity": "owner"
        }
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "recovery-link"
    },
    {
      "configuredBy": "oauth-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---



# Deployment administrator, Owner or Administrator or the related Member or the related Owner or Gateway client using Account token or execution under Recovery link or execution under OAuth settings may read Account

Deployment administrator and Owner manage Account profiles, budgets and counters. Administrator management is limited to Member-associated targets; Member creation is supported, while Administrator assignment and first Owner establishment require full administration. An invitation or configured OAuth registration can establish its authorized Account. Related Member and Owner role holders manage their own password and security; request-preference changes additionally require the Account's current Policy permission. A valid presented recovery authority replaces its subject's password; a valid credit authority adds its face value to that Account's budget. Pausing and physical deletion exclude Owner-associated Accounts.

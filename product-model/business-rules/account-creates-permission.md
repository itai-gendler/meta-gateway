---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        }
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
      ]
    },
    {
      "configuredBy": "invitation-code"
    },
    {
      "configuredBy": "oauth-settings",
      "when": [
        {
          "entity": "oauth-settings",
          "fact": "Registration",
          "is": true
        }
      ]
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




# Deployment administrator, Owner or Administrator or execution under Invitation code or execution under OAuth settings may create Account

Deployment administrator and Owner manage Account profiles, budgets and counters. Administrator management is limited to Member-associated targets; Member creation is supported, while Administrator assignment and first Owner establishment require full administration. An invitation or configured OAuth registration can establish its authorized Account. Related Member and Owner role holders manage their own password and security; request-preference changes additionally require the Account's current Policy permission. A valid presented recovery authority replaces its subject's password; a valid credit authority adds its face value to that Account's budget. Pausing and physical deletion exclude Owner-associated Accounts.

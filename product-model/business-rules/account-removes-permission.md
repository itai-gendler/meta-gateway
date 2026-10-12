---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "removes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ],
      "when": [
        {
          "entity": "owner",
          "fact": "Account association",
          "absent": true
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




# Deployment administrator, Owner may remove Account

Deployment administrator and Owner manage Account profiles, budgets and counters. Administrator management is limited to Member-associated targets; Member creation is supported, while Administrator assignment and first Owner establishment require full administration. An invitation or configured OAuth registration can establish its authorized Account. Related Member and Owner role holders manage their own password and security; request-preference changes additionally require the Account's current Policy permission. A valid presented recovery authority replaces its subject's password; a valid credit authority adds its face value to that Account's budget. Pausing and physical deletion exclude Owner-associated Accounts. Owner row protection still applies to final removal when dependent cleanup has already received the requested ID.
